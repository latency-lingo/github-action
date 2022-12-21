
# Latency Lingo Github Action

Publish performance test results to [Latency Lingo](https://latencylingo.com) as part of your CI/CD pipeline.

I recommend visiting the [Latency Lingo documentation](https://docs.latencylingo.com) to get familiar.

![](assets/logo_full.png)

## Usage
Locate your API key in [account settings](https://latencylingo.com/account/api-access) and add it as a secret to your Github repository. Next, add the Github Action as a step in your workflow.

The input arguments mimic the flags provided to the [`publish`](https://docs.latencylingo.com/docs/cli/commands/publish) CLI command.

The value of `file` should reference a file containing your test results. This depends on your test runner and strategy for running tests in CI/CD. Feel free to [reach out](mailto:support@latencylingo.com) for any support.

The action evaluates any thresholds for the test scenario referenced. If any of the thresholds are violated, the action will fail the build.

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

## References
- [Latency Lingo](https://latencylingo.com)
- [Github workflow syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- [Integration on Github Marketplace](https://github.com/marketplace/actions/latency-lingo-performance-test-coverage)
- [Integration Github repository](https://github.com/latency-lingo/github-action)
