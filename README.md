
# Latency Lingo Github Action

Publish performance test results to [Latency Lingo](https://latencylingo.com) as part of your CI/CD pipeline.

I recommend visiting the [Latency Lingo documentation](https://docs.latencylingo.com) to get familiar.

![](assets/logo_full.png)

## Usage
Locate your API key in your [account settings](https://latencylingo.com/account/api-access) and add it as a secret to your Github repository. Next, add the Github Action as a step in your workflow.

The value of `file` should be the path to the file containing your test results. This depends on your test runnner and strategy for running tests in CI/CD. Feel free to [reach out](mailto:support@latencylingo.com) for any support.

## Examples
```yml
- name: Latency Lingo
  uses: latency-lingo/github-action@v0.0.1
  with:
    api-key: ${{ secrets.LATENCY_LINGO_API_KEY }}
    file: jmeter-results.jtl
    label: github-action-test
```

```yml
- name: Latency Lingo
  uses: latency-lingo/github-action@v0.0.1
  with:
    api-key: ${{ secrets.LATENCY_LINGO_API_KEY }}
    file: gatling-results.log
    label: github-action-gatling-test
    format: gatling
```
