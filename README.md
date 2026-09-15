# Components that Refuse to be Cached in CacheView

This repository contains sample applications, validation assets, and evidence used to validate ASP.NET Core Issue #69125 - Components that refuse to be cached in CacheView.

## Repository Purpose

The samples in this repository validate CacheView behavior when components depend on per-request state and cannot be safely cached without appropriate cache variations. The validation covers:

- AuthorizeView cache refusal and VaryByUser requirements
- QuickGrid cache refusal and VaryByQuery requirements
- Custom component cache refusal using `CacheBehavior.Throw`
- Custom component live rerender behavior using `CacheBehavior.Rerender`
- Cookie-based cache variations
- Nested CacheView restrictions
- CacheView exception message usability and guidance

## Contents

- Static SSR sample application
- Razor Class Library containing custom cache-aware components
- Validation report and test results
- Screenshots and video evidence
- Documentation assessment findings

## Prerequisites

- .NET SDK 11.0.100-rc.1.26425.128
- Visual Studio 2026 Preview (or later)

The repository uses a `global.json` file that pins the SDK version to .NET 11 RC1 to ensure consistent builds and reproducible validation results.

## Repository Structure

```text
CacheViewRefusalValidation
│
├── Samples
│   └── CacheViewValidationSSR
│
├── CacheViewValidationComponents
│
├── Evidence
    └── ValidationReport
    └── Screenshots and Videos
```

## Deployment / Running the Samples

```bash
git clone https://github.com/BrundhaVelusamy/CacheViewRefusalValidation.git

cd CacheViewRefusalValidation
cd Samples/CacheViewValidationSSR

dotnet restore
dotnet build
dotnet run
```

## Application URL

After running the application, the ASP.NET Core development server displays the active URL(s) in the console output.

Expected URL:

```text
https://localhost:5054
```