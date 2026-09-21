# Swimlanes Diagram

* process vs responsibility
* Reference [mermaid docs swimlanes](https://mermaid.ai/open-source/syntax/swimlanes.html)

## AS-IS Operational Flow

```mermaid
swimlane-beta TB
  subgraph SourceRepositories
    scRepo[SC Repo with Plaintext Secrets]
    appianRepo[BPM Repo with Plaintext Secrets]
  end

  subgraph ExecutionEngines
    scRunner[Sitecore Engine with Transient Retries]
    appianRunner[Legacy BPM Engine without Retries]
  end

  subgraph DatabaseLayer
    targetDbs[Target Databases ADS and Sitecore]
  end

  subgraph DownstreamTests
    divergentJson[Divergent JSON Test Data Files]
    testSuites[Downstream Automation Test Suites]
  end

  scRepo --> scRunner
  appianRepo --> appianRunner
  scRunner --> targetDbs
  appianRunner --> targetDbs
  targetDbs --> divergentJson --> testSuites
```
