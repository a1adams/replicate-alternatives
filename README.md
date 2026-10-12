# Replicate Alternative Platforms: 8 Hosts Compared on Deploys and Webhooks

This Replicate alternative list compares 8 hosts, checked against vendor docs on 11 October 2026 and ranked by how much of a model pipeline one API call can run and report back on. Wireflow is first because one POST runs a whole saved workflow of several models, and a completion webhook returns the result. Of the 8, 6 also let you deploy your own model, which Wireflow does not.

1. **Wireflow**: Best overall for running a multi-model chain from one API call, a hosted node canvas with a REST API
2. **fal**: Best for hosted models and your own serverless apps behind one queue, a generative media API
3. **Baseten**: Best for engineering teams serving their own models in production, with Truss packaging and Chains
4. **RunPod Serverless**: Best for running your own container on GPUs that scale to zero, built around a handler function
5. **Runware**: Best for bulk image jobs where each item reports back on its own, a pay-per-request API
6. **WaveSpeedAI**: Best for calling many hosted models with a price quote first, one API key across a large catalog
7. **Modal**: Best for Python teams that write their own queue logic, a serverless platform billed per second
8. **Hugging Face Inference Endpoints**: Best for serving a Hub model on dedicated hardware, managed endpoints billed by the minute

We build Wireflow, so read entry 1 with that in mind. [Wireflow's AI workflow builder page](https://www.wireflow.ai/ai-workflow-builder) shows the canvas where the workflows in entry 1 are built, and every other entry links to its vendor's own docs so each line can be checked.

The tables below are generated from [`data/tools.json`](data/tools.json). Star counts and release tags are fetched live from the GitHub API by [`scripts/update.js`](scripts/update.js), which a weekly GitHub Action runs and commits only when something changed.

<!-- LAST-CHECKED:START -->
Live repository data last checked **2026-10-12** by [`scripts/update.js`](scripts/update.js), which runs weekly via GitHub Actions.
<!-- LAST-CHECKED:END -->

Maintained by [a1adams](https://github.com/a1adams). Corrections are welcome, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contents

- [The data](#the-data)
- [Capability scores](#capability-scores)
- [Comparison table](#comparison-table)
- [The tools](#the-tools)
  - [Wireflow](#1-wireflow)
  - [fal](#2-fal)
  - [Baseten](#3-baseten)
  - [RunPod Serverless](#4-runpod-serverless)
  - [Runware](#5-runware)
  - [WaveSpeedAI](#6-wavespeedai)
  - [Modal](#7-modal)
  - [Hugging Face Inference Endpoints](#8-hugging-face-inference-endpoints)
- [Replicate, the baseline](#replicate-the-baseline)
- [What each check means](#what-each-check-means)
- [How this list is maintained](#how-this-list-is-maintained)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## The data

One row per tool, one column per thing people actually check before committing. Columns with nothing verified behind them are dropped rather than filled with guesses.

<!-- DATA-TABLE:START -->
| Tool | Claude connection | REST API | Free tier | Pricing | Open-source SDK / MCP |
|---|---|---|---|---|---|
| **[Wireflow](#1-wireflow)** | Claude connector over MCP, OAuth | Yes | [check](https://www.wireflow.ai/pricing) | [pricing](https://www.wireflow.ai/pricing) | n/a |
| **[fal](#2-fal)** | Hosted MCP, Streamable HTTP, OAuth | Yes | [check](https://fal.ai/pricing) | [pricing](https://fal.ai/pricing) | [fal-ai/fal](https://github.com/fal-ai/fal), 968 ★, fal_v1.81.4 |
| **[Baseten](#3-baseten)** | Management MCP, dedicated API key | Yes | [check](https://www.baseten.co/pricing) | [pricing](https://www.baseten.co/pricing) | [basetenlabs/truss](https://github.com/basetenlabs/truss), 1,219 ★, v0.18.33 |
| **[RunPod Serverless](#4-runpod-serverless)** | Hosted MCP or npm package; manages infrastructure | Yes | [check](https://www.runpod.io/pricing) | [pricing](https://www.runpod.io/pricing) | [runpod/runpod-python](https://github.com/runpod/runpod-python), 316 ★, v1.12.0 |
| **[Runware](#5-runware)** | Hosted MCP, OAuth with an API-key form | Yes | [check](https://runware.ai/pricing) | [pricing](https://runware.ai/pricing) | [runware/runware-python](https://github.com/runware/runware-python), 3 ★, pushed 2026-10-10 |
| **[WaveSpeedAI](#6-wavespeedai)** | Local MCP via npx, API key | Yes | [check](https://wavespeed.ai/docs/how-pricing-works) | [pricing](https://wavespeed.ai/docs/how-pricing-works) | [WaveSpeedAI/wavespeed-python](https://github.com/WaveSpeedAI/wavespeed-python), 28 ★, v2.0.3 |
| **[Modal](#7-modal)** | n/a | n/a | [check](https://modal.com/pricing) | [pricing](https://modal.com/pricing) | [modal-labs/modal-client](https://github.com/modal-labs/modal-client), 523 ★, pushed 2026-10-12 |
| **[Hugging Face Inference Endpoints](#8-hugging-face-inference-endpoints)** | Endpoints MCP server, manages endpoints | Yes | [check](https://huggingface.co/docs/inference-endpoints/support/pricing) | [pricing](https://huggingface.co/docs/inference-endpoints/support/pricing) | [huggingface/huggingface_hub](https://github.com/huggingface/huggingface_hub), 3,982 ★, v2.2.0 |
<!-- DATA-TABLE:END -->

## Capability scores

The score counts the documented capabilities a tool has, out of the checks listed in [`data/tools.json`](data/tools.json) under `capabilityChecks`. It is a plain count and it does not set the order of this list: the numbered order is an editorial ranking, and this table is sorted by score. The checks and every answer are in the file, so each cell can be checked. Disagree with a cell? Open an issue naming the tool, the check and the evidence.

<!-- CAPABILITY-SCORES:START -->
| Tool | Runs a chain in one call | Completion webhook | Deploy your own model | Scale to zero | Official MCP server | Score |
|------|---|---|---|---|---|-------|
| **[fal](#2-fal)** | ✅ | ✅ | ✅ | ✅ | ✅ | **5/5** |
| **[Baseten](#3-baseten)** | ✅ | ✅ | ✅ | ✅ | ✅ | **5/5** |
| **[RunPod Serverless](#4-runpod-serverless)** | n/a | ✅ | ✅ | ✅ | ✅ | **4/5** |
| **[Runware](#5-runware)** | ❌ | ✅ | ✅ | ✅ | ✅ | **4/5** |
| **[Wireflow](#1-wireflow)** | ✅ | ✅ | n/a | n/a | ✅ | **3/5** |
| **[Hugging Face Inference Endpoints](#8-hugging-face-inference-endpoints)** | n/a | n/a | ✅ | ✅ | ✅ | **3/5** |
| **[WaveSpeedAI](#6-wavespeedai)** | ❌ | ✅ | n/a | n/a | ✅ | **2/5** |
| **[Modal](#7-modal)** | n/a | n/a | ✅ | ✅ | n/a | **2/5** |
<!-- CAPABILITY-SCORES:END -->

## Comparison table

| Tool | Best for | Pricing basis | Chain in one call | Completion webhook |
|---|---|---|---|---|
| **Wireflow** | Chains of hosted models | Credits per generation | Yes, a saved workflow | Yes, up to 12 attempts |
| **fal** | Hosted models plus your own apps | Per output, or per runner second | Yes, workflows/execute | Yes, up to 31 retries |
| **Baseten** | Serving your own models | Per minute of compute | Yes, Chains in Python | Yes, outputs not stored |
| **RunPod Serverless** | Your own container on GPUs | GPU rates on its pricing page | Not published | Yes, 2 more tries on failure |
| **Runware** | Bulk image jobs | Per request | No, tasks run independently | Yes, one per batch item |
| **WaveSpeedAI** | Many models, price quoted first | Per model, prepaid credits | No, separate requests | Yes, up to 3 retries |
| **Modal** | Your own Python pipelines | Per second of compute | Not published | Not published, you poll |
| **Hugging Face Inference Endpoints** | A Hub model on dedicated hardware | Per minute, hourly rates | Not published | Not published |

From each vendor's own docs and pricing pages, checked on 2026-10-11. Prices are not typed in this table, so follow the pricing links in the data table.

## The tools

### 1. Wireflow

*Best overall for running a multi-model chain from one API call*

![Wireflow screenshot](https://assets.wireflow.ai/competitors/wireflow-70f47ccd9660.png?v=r5)

- **What it is:** [Wireflow](https://www.wireflow.ai/) is a platform where ad teams and AI agents build and rerun creative on a shared node board. Each model is a node on one canvas, the output of one node feeds the next, and the same board runs from the canvas, from Claude or from your own code through the API.
- **Best for:** Teams whose Replicate code has turned into a chain of model calls, such as a prompt step, an image model and a video model, and who would rather call the whole chain once than pipe predictions together with webhooks.
- **Pricing basis:** Credits per generation, set by the model you run, and one credit is US$0.01. Starter is US$24 a month with 1,600 credits, and the free plan builds up to 5 workflows but cannot run generations. The [Wireflow pricing page](https://www.wireflow.ai/pricing) lists a credit price for every model (October 2026).
- **Standout:** You send only the input values to `POST /api/v1/workflows/{id}/run` and the saved workflow runs, so a chain of models is one request, as [the run endpoint docs](https://www.wireflow.ai/docs/api/run) show. Add a webhook block and Wireflow POSTs the result to your URL when the run finishes, signed with HMAC-SHA256 when you set a secret and retried for up to 12 attempts.
- **Limit:** Deploying your own model, container or custom code is not documented, because the API runs workflows built from the nodes in Wireflow's own node reference. If your Replicate account mostly serves a model you pushed with Cog, pick an entry below that hosts your own container. There is no official SDK, so you call the REST API with any HTTP client.
- **API or automation:** The REST API lives at `https://www.wireflow.ai/api/v1` and takes an API key as a Bearer token, and a new key starts read-only until you add scopes. A `metadata` object you send comes back verbatim in the webhook delivery. If you lack credits, the run call returns a 402 with the credit cost of each node, and a model that fails is not charged. Wireflow is also a Claude connector over MCP.
- **Sources:** the Wireflow pages linked in this entry, plus the API overview, webhooks and executions docs, checked 2026-10-11.
- **Links:**
  - [Wireflow AI workflow builder page](https://www.wireflow.ai/ai-workflow-builder)
  - [Docs](https://www.wireflow.ai/docs/api/overview)

Build on Wireflow when the job is a fixed chain of hosted models and your code only needs to send inputs and wait for one webhook. You hit a wall when the model you need is your own weights in your own container. The building side is shown step by step in [a worked example of chaining models behind one endpoint](https://www.wireflow.ai/features/chain-ai-models-api).

Run a saved workflow with a completion webhook, from the official Webhooks page. Replace the workflow ID, input, metadata and URL, and set WIREFLOW_API_KEY to your own key.
```bash
curl -X POST https://www.wireflow.ai/api/v1/workflows/cm1abc123/run \
  -H "Authorization: Bearer $WIREFLOW_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "inputs": { "node-prompt": "A cat wearing a top hat" },
    "metadata": { "jobId": "job_42" },
    "webhook": {
      "url": "https://yourapp.com/api/webhooks/wireflow",
      "secret": "whsec_your_signing_secret"
    }
  }'
```

### 2. fal

*Best for hosted models and your own serverless apps behind one queue*

![fal screenshot](https://assets.wireflow.ai/competitors/fal-ai-0ec799965278.png?v=r5)

- **What it is:** [fal](https://fal.ai/) is a generative media platform for developers, with 1,000+ image, video, audio and 3D models behind one API and SDKs. fal Serverless runs your own models and apps on the same queue, from a Python class or your own container image.
- **Best for:** Developers who want Replicate-style access to many hosted models and also need to deploy their own Python app or container on GPUs that scale from zero.
- **Pricing basis:** Pay per use. Hosted models are priced per output, for example Nano Banana 2 at $0.08 per image and Kling Video v2.5 Turbo Pro at $0.07 per second (fal pricing page, October 2026). On Serverless you pay per second for the time runners are alive, including setup and idle keep-alive time.
- **Standout:** A custom workflow is a JSON definition with an input node, as many fal model nodes as you want and an output node, and the `workflows/execute` endpoint runs it. That makes fal the closest entry to Wireflow on chaining.
- **Limit:** The fal team approves Serverless access for each account, and custom GPU deployments need a sales contact. Final cost shifts with resolution, duration and quality, so a price per output is a starting point rather than a quote.
- **API or automation:** Pass a `webhook_url` with a queue request and fal POSTs the result when processing completes, retrying a failed delivery up to 31 times. `min_concurrency` defaults to 0 on Serverless, and an OAuth MCP server lets an assistant find models, check pricing and run generations.
- **Sources:** [Serverless introduction](https://fal.ai/docs/documentation/serverless), [webhooks](https://fal.ai/docs/documentation/model-apis/inference/webhooks), [custom workflow tutorial](https://fal.ai/docs/examples/integrations/custom-workflow-ui), [scaling parameters](https://fal.ai/docs/documentation/deployment/scale-your-application), [Serverless pricing](https://fal.ai/docs/documentation/serverless/pricing), [MCP server](https://fal.ai/docs/documentation/setting-up/mcp), checked 2026-10-11.
- **Links:**
  - [Pricing](https://fal.ai/pricing)
  - [fal-ai/fal](https://github.com/fal-ai/fal)

Pick fal over Wireflow when you need your own model behind the same queue as the hosted ones and you are happy to write the workflow JSON yourself. The longer trade-offs between hosted catalogs and container hosts are in [our Replicate alternative guide](https://www.wireflow.ai/blog/replicate-alternative).

Install the fal CLI, from fal's Serverless docs. Then test an app with fal run and ship it with fal deploy.
```bash
pip install fal
```

### 3. Baseten

*Best for engineering teams serving their own models in production*

![Baseten screenshot](https://assets.wireflow.ai/competitors/baseten-4d376d9473b0.png?v=r5)

- **What it is:** [Baseten](https://www.baseten.co/) is a production inference platform for deploying open-source and custom AI models. You package a model with Truss and push it with `baseten model push`, or deploy an existing server image as a custom Docker server.
- **Best for:** Engineering teams that serve their own models in production and want to pay for compute by the minute.
- **Pricing basis:** Compute charged by the minute, with no charge for idle time. The Basic plan is $0 a month and pay as you go, and the cheapest GPU listed is a T4 at $0.01052 per minute (Baseten pricing page, October 2026). New accounts receive credits, and the amount is not stated.
- **Standout:** Chains is Baseten's Python framework for building and deploying multi-step, multi-model inference pipelines, which covers the chaining that Replicate leaves to webhooks.
- **Limit:** Baseten does not store model outputs, so if webhook delivery fails after all retries the result is lost unless your model saves it itself. Pro and Enterprise pricing is by quote, and compute in other regions needs a sales contact.
- **API or automation:** An async request returns a request ID at once, and Baseten POSTs the output to your webhook when inference completes, with requests able to queue for up to 72 hours. A deployment scales to zero through the dashboard or the Management API, and a management MCP server at `https://api.baseten.co/mcp` takes a dedicated API key.
- **Note:** The linked repository is Truss, Baseten's model packaging framework.
- **Sources:** [Develop a model](https://docs.baseten.co/development/model/overview), [async inference](https://docs.baseten.co/inference/async), [Chains overview](https://docs.baseten.co/development/chain/overview), [scale a deployment](https://docs.baseten.co/deployment/manage/scaling), [connect your coding agent](https://docs.baseten.co/agent-setup), checked 2026-10-11.
- **Links:**
  - [Pricing](https://www.baseten.co/pricing)
  - [basetenlabs/truss](https://github.com/basetenlabs/truss)

Pick Baseten over fal when the models are yours and the pipeline logic belongs in Python you review, not in a JSON definition. Write each output to your own storage from inside the model, because the webhook delivery is the only copy Baseten sends.

Create a development deployment from a Truss directory, from the official Develop a model page.
```bash
baseten model push --watch
```

### 4. RunPod Serverless

*Best for running your own container on GPUs that scale to zero*

![RunPod Serverless screenshot](https://assets.wireflow.ai/competitors/runpod-07375e55f557.png?v=r5)

- **What it is:** [RunPod Serverless](https://www.runpod.io/) gives you autoscaling GPU endpoints. You write a handler function, package it with its dependencies in a Docker image and deploy it to an endpoint.
- **Best for:** Developers who already have a model in a container and want production GPU endpoints that cost nothing between bursts of traffic.
- **Pricing basis:** RunPod lists Serverless GPU rates per GPU type on its pricing page, and flex workers cost nothing when they are not in use (RunPod docs, October 2026). The pricing page does not state the billing rule in words, so no rate is quoted here.
- **Standout:** Flex workers scale to zero when idle, and the site claims sub-200ms cold starts with FlashBoot and scaling from 0 to hundreds of workers in under 250ms.
- **Limit:** Flex workers incur cold starts when they scale up, and the active workers that avoid them run 24/7. Running several models in order from one request is not published as a feature, and Global Volumes for Serverless are in beta.
- **API or automation:** A job sent to `/run` can name a webhook URL, and if the call fails RunPod retries up to 2 more times with a 10-second delay. SDKs exist for Python, JavaScript and Go, and the Runpod API MCP server manages Pods, Serverless endpoints and templates.
- **Sources:** [workers overview](https://docs.runpod.io/serverless/workers/overview), [send requests](https://docs.runpod.io/serverless/endpoints/send-requests), [Serverless SDKs](https://docs.runpod.io/serverless/sdks), [MCP servers](https://docs.runpod.io/get-started/mcp-servers), checked 2026-10-11.
- **Links:**
  - [Pricing](https://www.runpod.io/pricing)
  - [runpod/runpod-python](https://github.com/runpod/runpod-python)

Pick RunPod Serverless over Baseten when you want to own the container and the handler, and a plain HTTP job with a webhook is all the orchestration you need. A two-model job becomes two requests, or one handler that calls both models.

Install the Python SDK, from the official Serverless SDKs page (Python 3.10 or higher).
```bash
pip install runpod
```

### 5. Runware

*Best for bulk image jobs where each item reports back on its own*

![Runware screenshot](https://assets.wireflow.ai/competitors/runware-1dad906299e3.png?v=r5)

- **What it is:** [Runware](https://runware.ai/) is an AI infrastructure platform with pay-as-you-go APIs for image, video, audio, LLM and 3D models. Runware Serverless also runs your own model code from a Python codebase or a container image, and releases its workers when traffic stops.
- **Best for:** Developers generating images in bulk through an API who want each result delivered as soon as it is ready.
- **Pricing basis:** Per request, for example FLUX 3 Image at $0.041 per image and Recraft V4.1 Flash at $0.007 (Runware pricing page, October 2026), and you are charged only for successful requests. Business-email sign-ups get $2 in free credits.
- **Standout:** Every request is an array of tasks processed independently, and with a `webhookURL` set, each completed item in a batch triggers its own webhook call, so a worker can store results one by one.
- **Limit:** Because tasks in one call are independent, one request does not chain models. Exact cost depends on the request parameters, so you estimate it in the Playground first.
- **API or automation:** A TypeScript SDK and a Python SDK wrap the REST and WebSocket transports and validate each request against the model's JSON Schema. The Model Upload API adds your own checkpoints and LoRAs, and a hosted MCP server at `https://mcp.runware.ai` uses OAuth with an API-key form.
- **Sources:** [Models API introduction](https://runware.ai/docs/models-api/introduction), [webhooks](https://runware.ai/docs/models-api/webhooks), [Model Upload](https://runware.ai/docs/models-api/model-upload), [Serverless introduction](https://runware.ai/docs/serverless/introduction), [MCP](https://runware.ai/docs/tools/mcp), checked 2026-10-11.
- **Links:**
  - [Pricing](https://runware.ai/pricing)
  - [runware/runware-python](https://github.com/runware/runware-python)

Pick Runware over RunPod Serverless when most jobs are hosted models in volume rather than your own container, and per-item webhooks suit your queue. Keep the chaining in your own worker, because the API runs each task on its own.

Install the Python SDK, from the official Python SDK page (Python 3.11 or higher).
```bash
pip install runware-sdk
```

### 6. WaveSpeedAI

*Best for calling many hosted models with a price quote first*

![WaveSpeedAI screenshot](https://assets.wireflow.ai/competitors/wavespeed-2d81973fb165.png?v=r5)

- **What it is:** [WaveSpeedAI](https://wavespeed.ai/) is a platform with 1000+ image, video, audio, 3D and LLM models behind a single API key.
- **Best for:** Developers who want one API across many generative models and have no model of their own to deploy.
- **Pricing basis:** Usage-based and set per model, with no subscription, so you top up credits and see the estimated price on the Run button before a generation. For example, nano-banana-2.1 text-to-image is listed at $0.04, shown discounted to $0.036 (WaveSpeedAI homepage, October 2026).
- **Standout:** Its MCP server has a `get_price` tool that quotes a price before a run, and it installs in Claude Code with one line: `claude mcp add wavespeed -- npx -y @wavespeed/mcp`.
- **Limit:** Self-serve deployment of your own model is not published, and the Enterprise page offers help deploying custom models instead. The workflow tutorial chains models as separate requests and polls each step before starting the next.
- **API or automation:** Add a `webhook` query parameter and WaveSpeedAI POSTs to your HTTPS endpoint when a task completes or fails, with up to 3 retries on a failed delivery. Sync mode cannot be combined with a webhook.
- **Sources:** [how to use webhooks](https://wavespeed.ai/docs/how-to-use-webhooks), [complete workflow tutorial](https://wavespeed.ai/docs/complete-workflow-tutorial), [how pricing works](https://wavespeed.ai/docs/how-pricing-works), [Enterprise](https://wavespeed.ai/enterprise), [WaveSpeedAI MCP server](https://github.com/WaveSpeedAI/mcp-server), checked 2026-10-11.
- **Links:**
  - [WaveSpeedAI/wavespeed-python](https://github.com/WaveSpeedAI/wavespeed-python)

Pick WaveSpeedAI over Runware when you call a wide spread of hosted models and want an agent to check the price before it spends credits. Budget for your own orchestration, because a three-model job is three requests and three webhooks or polls.

Add the MCP server to Claude Code, from the official WaveSpeedAI/mcp-server README. Set WAVESPEED_API_KEY first.
```bash
claude mcp add wavespeed -- npx -y @wavespeed/mcp
```

### 7. Modal

*Best for Python teams that write their own queue logic*

![Modal screenshot](https://assets.wireflow.ai/competitors/modal-1e254b935748.png?v=r5)

- **What it is:** [Modal](https://modal.com/) is a serverless cloud platform that runs Python workloads on GPUs and CPUs and bills per second. The `modal deploy` command creates and persists an App and its Functions, so repeated calls reuse the deployed code.
- **Best for:** Developers who want to run model inference or batch jobs in their own Python code without managing servers.
- **Pricing basis:** Starter is $0 plus compute, with $30 a month in free credits, and a T4 GPU costs $0.000164 per second (Modal pricing page, October 2026). Modal bills during load time and processing, and by default keeps containers alive for 60 seconds after the last input, which is billed too.
- **Standout:** Functions scale to zero by default, and any Python function becomes a persistent HTTPS endpoint with the `@modal.fastapi_endpoint` decorator and `modal deploy`.
- **Limit:** A completion webhook for spawned jobs is not described in the job-queue guide, which polls with `FunctionCall.get()`. Starter caps at 100 containers and 10 GPU concurrency, with 1 day of log retention.
- **API or automation:** The job-queue pattern submits work with `.spawn()`, which returns a call ID, and the result stays available for up to 7 days after completion. Running several models in order is not published as a platform feature, so the chain lives in your own code.
- **Sources:** [managing deployments](https://modal.com/docs/guide/managing-deployments), [job queues](https://modal.com/docs/guide/job-queue), [scaling out](https://modal.com/docs/guide/scale), [web endpoints](https://modal.com/docs/guide/webhooks), checked 2026-10-11.
- **Links:**
  - [Pricing](https://modal.com/pricing)
  - [modal-labs/modal-client](https://github.com/modal-labs/modal-client)

Pick Modal over WaveSpeedAI when the pipeline is your own Python and you want the platform to stay out of the way. Plan to add your own callback to the job, because the guide we read polls for the result.

Deploy an app, from the official Managing deployments guide (the module name is the guide's example).
```bash
modal deploy -m whisper_pod_transcriber.main
```

### 8. Hugging Face Inference Endpoints

*Best for serving a Hub model on dedicated hardware*

![Hugging Face Inference Endpoints screenshot](https://assets.wireflow.ai/competitors/huggingface-inference-endpoints-6f8a717555ff.png?v=r5)

- **What it is:** [Hugging Face Inference Endpoints](https://huggingface.co/docs/inference-endpoints/index) is a managed service from Hugging Face that deploys your AI model to production on dedicated infrastructure.
- **Best for:** Teams that want to host one specific model, from the Hub or from their own container, on dedicated CPUs or GPUs without managing servers.
- **Pricing basis:** Billed by the minute at an hourly rate, from $0.033 an hour for an AWS CPU instance and $0.5 an hour for a T4 GPU (Hugging Face pricing docs, October 2026). It needs an account with an active subscription and a card on file.
- **Standout:** You can customize serving with a handler.py file in the model repository or bring your own container image, and the service supports vLLM, TGI or a custom container, with autoscaling, logs and metrics.
- **Limit:** An async queue with a completion webhook is not described in the docs. With scale to zero, an idle endpoint meets a cold start, the proxy answers 503 while the new replica initializes, and you pay while the endpoint is initializing or running.
- **API or automation:** You call each endpoint over HTTP. The Inference Endpoints MCP server lets an assistant list, create, update, pause, resume, scale to zero, delete and test endpoints.
- **Note:** The linked repository is huggingface_hub, which manages Inference Endpoints from Python.
- **Sources:** [Inference Toolkit and custom handlers](https://huggingface.co/docs/inference-endpoints/engines/toolkit), [custom container](https://huggingface.co/docs/inference-endpoints/engines/custom_container), [autoscaling](https://huggingface.co/docs/inference-endpoints/guides/autoscaling), [pricing](https://huggingface.co/docs/inference-endpoints/support/pricing), [MCP server](https://huggingface.co/docs/inference-endpoints/guides/mcp_server), checked 2026-10-11.
- **Links:**
  - [huggingface/huggingface_hub](https://github.com/huggingface/huggingface_hub)

Pick Hugging Face Inference Endpoints over Modal when the model already lives on the Hub and you want it served with no code beyond a handler. Because no completion webhook is published, plan for synchronous calls or put your own queue in front of the endpoint.

Install huggingface_hub, which manages Inference Endpoints from Python, from the official huggingface_hub installation page.
```bash
pip install --upgrade huggingface_hub
```

## Replicate, the baseline

Replicate is the platform this list is measured against, so it is described here and not ranked. These lines come from Replicate's own pages, checked 2026-10-11.

- **What it is:** [Replicate](https://replicate.com/) is a platform to run and fine-tune models and deploy custom models through a cloud API.
- **Deploys:** You package your own model with Cog, an open source tool that puts a machine learning model in a Docker container, and push it to Replicate as a cloud API. Source: [push your own model](https://replicate.com/docs/guides/build/push-a-model).
- **Webhooks and pipelines:** A webhook delivers a completed prediction's metadata and outputs to your URL, and the docs describe model pipelines as capturing one prediction's output with a webhook and piping it into another model. Source: [Replicate webhooks](https://replicate.com/docs/topics/webhooks).
- **Scaling:** Deployments autoscale with demand, and you can cap the number of instances to limit spend or set a minimum to keep instances warm. Source: [Replicate deployments](https://replicate.com/docs/topics/deployments).
- **Billing:** Some models bill per output, for example flux-dev at $0.025 per image, and others per second of hardware time, and private models bill for all the time their instances are online, including setup and idle time (Replicate pricing page, October 2026).
- **MCP:** Replicate publishes a remote MCP server and the `replicate-mcp` npm package, and both support all of the operations in its HTTP API. Source: [Replicate's MCP server](https://replicate.com/docs/reference/mcp).

## What each check means

A check means the vendor's own docs describe it. A cross means the docs say it works another way. Anything in brackets without a mark means not published, or not verified for this list, which is not proof that it is absent.

- **Runs a chain in one call:** A documented feature runs several models in order from one request. Code you write yourself inside one deployment does not count.
- **Completion webhook:** You give a URL with the request and the platform POSTs the result when the job finishes.
- **Deploy your own model:** You can put your own model, code or container behind the platform's API without a sales process.
- **Scale to zero:** Idle capacity for your deployment can drop to zero instances.
- **Official MCP server:** The vendor publishes an MCP server that an agent can connect to.

## How this list is maintained

Every line comes from the vendor's own docs, pricing pages and GitHub READMEs, read on 11 October 2026. For each host we read the deploy guide, the webhook or async page, the scaling page and the MCP page. The numbered order is editorial and follows 4 checks in this order: whether one API call can run a chain of models, how a finished job reports back (webhook, polling or nothing), whether you can deploy your own model, and how idle capacity is billed. Nothing here was benchmarked, so no cold start was timed and no price was tested. Replicate is the baseline and is not ranked, and hosts we had not checked against their own docs by that date are left out.

To correct a line, open an issue or a pull request with the tool, the check and a link to the vendor page that proves it. Corrections to entry 1 are welcome too.

- [`data/tools.json`](data/tools.json) is the source of truth. The tables in this README are generated from it and are overwritten on every run, so edit the JSON, not the tables.
- [`scripts/update.js`](scripts/update.js) fetches star counts and latest release tags from the GitHub API for the tools that publish an official repo, stamps the check date, and regenerates the tables. `--offline` regenerates without the network; `--check` exits non-zero if the README has drifted from the data.
- [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml) runs it weekly and on manual dispatch, and commits only when the data actually changed.
- Prices are deliberately not stored as numbers. A stale price in a comparison table is worse than no price, so the table links to each vendor's own pricing page.

## FAQ

<details>
<summary><strong>What is a good Replicate alternative for running multi-step AI image and video workflows?</strong></summary>

Wireflow, fal and Baseten are the 3 entries here that run a chain of models from one request. Wireflow runs a saved workflow built on a canvas, fal runs a workflow JSON through `workflows/execute`, and Baseten runs Chains written in Python. The other 5 leave the chain to your own code.

</details>

<details>
<summary><strong>Can I chain multiple Replicate models together?</strong></summary>

Yes, but in your own code. Replicate's docs describe a pipeline as capturing one prediction's output with a webhook and piping it into the next model, one prediction at a time. If you want one request in and one result out, the chaining entries above do that on the platform side.

</details>

<details>
<summary><strong>Can I run custom models on these platforms?</strong></summary>

On 6 of the 8, yes. fal (after account approval), Baseten, RunPod Serverless, Runware, Modal and Hugging Face Inference Endpoints all document deploying your own model or container. WaveSpeedAI offers help with custom models through Enterprise, and Wireflow does not document own-model deploys.

</details>

<details>
<summary><strong>What is the difference between fal and Replicate?</strong></summary>

Both host many models behind one API and let you deploy your own. fal adds the `workflows/execute` endpoint, which runs several model nodes from one request, while Replicate's docs build pipelines from webhooks between predictions. fal Serverless needs account approval, and Replicate pushes your model with Cog.

</details>

<details>
<summary><strong>What happens to my Replicate webhooks if I move?</strong></summary>

Six of the 8 hosts document a completion webhook, so the pattern carries over, with Modal and Hugging Face Inference Endpoints as the exceptions. Retry rules differ, from 2 extra tries on RunPod to 31 on fal. Wireflow can sign its deliveries and echoes your metadata, as [the Wireflow webhook docs](https://www.wireflow.ai/docs/api/webhooks) describe.

</details>

<details>
<summary><strong>Which platform is best for a startup with variable traffic?</strong></summary>

Pick one that scales your deployment to zero. fal, Baseten, RunPod Serverless flex workers, Runware Serverless, Modal and Hugging Face Inference Endpoints all document it, with a cold start on the next request. Wireflow and WaveSpeedAI run a hosted catalog, so there is no deployment of yours to keep warm.

</details>

<details>
<summary><strong>Is Wireflow a direct Replicate replacement?</strong></summary>

Not for hosting your own model, because Wireflow does not document own-model deploys. It replaces Replicate when your code chains hosted models, since one API call runs the whole saved workflow and a webhook returns the result. If your own model is the core of the job, start with entry 3 or 4 instead.

</details>

## The short version

Pick Wireflow when your Replicate code has become a chain of hosted models and you want one call in and one webhook out. Pick fal, the next entry, when you also need your own model on the same queue and are happy to write the workflow JSON. If the job is one model you own, Baseten, RunPod Serverless and Modal are stronger homes for it. Before you move, rebuild one real pipeline on your two finalists and count the requests, retries and lines of glue code each one needs. For entry 1, the next page to read explains [how one workflow runs several models](https://www.wireflow.ai/multi-model-ai-workflow).

## Contributing

Corrections and additions are welcome, including corrections to the entry for the tool that maintains this list. Open an issue with the tool name, a working link, one line on what it does that the tools already listed do not, and one line on where it stops. Entries are judged on whether they are usable today, not on popularity. Full rules in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0 Universal](LICENSE), public domain. Take the data, fork the list, no attribution required.

---

Maintained by [a1adams](https://github.com/a1adams).
