# LLM Workflow Engine (LWE) Data Query plugin

Data Query plugin for [LLM Workflow Engine](https://github.com/llm-workflow-engine/llm-workflow-engine)

Send natural language commands to a loaded file of structured data.

## Installation

### From packages

Install the latest version of this software directly from github with pip:

```bash
pip install git+https://github.com/llm-workflow-engine/lwe-plugin-data-query
```

### From source (recommended for development)

Install the latest version of this software directly from git:

```bash
git clone https://github.com/llm-workflow-engine/lwe-plugin-data-query.git
```

Install the development package:

```bash
cd llm-workflow-engine
pip install -e .
```

## Configuration

Add the following to `config.yaml` in your profile:

```yaml
plugins:
  enabled:
    - data_query
    # Any other plugins you want enabled...
  # These are the default values.
  data_query:
    agent:
      verbose: true
```

## Usage

From a running LWE shell:

```
/data-query load test.csv
/data-query Find users with last name "Smith".
/data-query unload
```

## Caveats

Large datasets will be chunked before sending to the LLM, in this case
the LLM may not be able to consider the full data set when formulating
a response.
