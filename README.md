# Vegetation Management Process API

A MuleSoft reference implementation for submitting vegetation imagery to analysis services and returning structured observations for inspection and risk-review workflows.

> **Project status:** Demonstration implementation. Model outputs, confidence values, accuracy figures, and risk classifications require validation against representative utility datasets before operational use.

## Utility use case

Vegetation management affects reliability, inspection planning, right-of-way maintenance, wildfire mitigation, and field safety. This project demonstrates an API boundary that can normalize image-analysis requests and results without coupling utility workflows to one model provider.

## Capabilities

- single-image and batch analysis;
- vegetation-health and coverage observations;
- species or object identification where supported by the selected model;
- location and inspection metadata;
- asynchronous status retrieval;
- normalized confidence, risk and recommendation fields.

## Architecture

| Component | Responsibility |
|---|---|
| Mule API | Validation, security, orchestration and normalized contracts |
| Model adapter | Provider-specific request and response handling |
| Analysis model | Image classification, detection or segmentation |
| Utility workflow | Inspection review, prioritization and work creation |

## Responsible-use boundaries

Model output should be treated as decision support. A production design should include:

- representative model evaluation and documented thresholds;
- human review before work prioritization or safety conclusions;
- image provenance, timestamp and geospatial accuracy;
- retention and privacy controls;
- model and prompt/version traceability;
- monitoring for drift, false negatives and seasonal effects;
- safe handling of unavailable or low-confidence results.

## API operations

- `POST /vegetation/analyze`
- `POST /vegetation/batch-analyze`
- `GET /vegetation/status/{analysisId}`
- `GET /health`

Inspect the RAML and Mule flows for the authoritative contract and implementation details.

## Portfolio context

This repository is part of a broader [utility grid-modernization portfolio](https://github.com/msaleme/utility-ai-mulesoft-api/blob/master/docs/portfolio-guide.md) covering grid intelligence, field operations, smart meters, customer programs, compliance, and governed AI-assisted operations.


## Related projects

- [Utility Field Operations Support Agent](https://github.com/msaleme/field-operations-support-agent)
- [Utility AI Semantic Layer](https://github.com/msaleme/utility-ai-mulesoft-api)

## License

See the repository license, if present, and verify the terms of every external model before redistribution or commercial use.
