# Getting Started with the Syncfusion Blazor File Upload Component

## Overview

This sample demonstrates the Syncfusion [Blazor File Upload](https://www.syncfusion.com/blazor-components/blazor-file-upload) a Blazor Server application. The project showcases how to upload single or multiple files, apply file validation, and perform file save and remove operations. It provides a practical reference for developers building document upload workflows, content submission portals, and file management scenarios in Blazor applications.

The application is built using ASP.NET Core Blazor Server and Syncfusion Blazor UI components. The sample includes upload processing scenarios and demonstrates how file operations can be integrated into a server-hosted application architecture.

## Key Features

- Demonstrates the Syncfusion Blazor File Upload (`SfUploader`) component in a Blazor Server application.
- Restricts uploads to specific document formats using the `AllowedExtensions` property:
  - `.pdf`
  - `.docx`
  - `.xls`
  - `.xlsx`
- Validates file size during selection using:
  - `MinFileSize="1000"` (1 KB minimum)
  - `MaxFileSize="1000000"` (1 MB maximum)
- Enables automatic upload processing with the `AutoUpload="true"` property.
- Handles file selection and upload through the `ValueChange` event (`OnChange` method).
- Saves uploaded files directly to the application's `wwwroot` directory using `FileStream` and `OpenReadStream()`.
- Supports client-side file removal through the `OnRemove` event (`OnRemove` method).
- Deletes previously uploaded files from the `wwwroot` directory when users remove files from the uploader.
- Uses the `BeforeRemove` event to configure removal behavior by setting `args.PostRawFile = false`.
- Includes a server-side API controller (`SampleDataController`) demonstrating upload and delete operations through:
  - `Save(IList<IFormFile> UploadFiles)`
  - `Remove(string UploadFiles)`
- Shows how uploaded files can be persisted using ASP.NET Core `IFormFile` processing.
- Prevents duplicate file creation in the API-based save implementation by checking file existence before storing files.
- Returns custom HTTP response information when attempting to upload an existing file.
- Demonstrates file deletion using ASP.NET Core file system APIs.
- Contains commented `UploaderAsyncSettings` configuration illustrating how to connect the uploader to API endpoints:
  - `api/SampleData/Save`
  - `api/SampleData/Remove`

## Prerequisites

- [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) or [Visual Studio Code](https://code.visualstudio.com/)
- [.NET SDK](https://dotnet.microsoft.com/en-us/download/dotnet) compatible with the project's target framework

## How to Run the Project

**Visual Studio 2022**

1. Clone or download this repository.
2. Open the `BlazorFileUpload.sln` solution file.
3. Restore NuGet packages when prompted.
4. Ensure the `BlazorFileUpload` project is selected as the startup project.
5. Build the solution.
6. Run the application using `Ctrl+F5`.

**Visual Studio Code**

1. Open the repository folder in Visual Studio Code.
2. Open the integrated terminal.
3. Navigate to the project folder.

```bash
dotnet restore
dotnet run
```

4. Open the local URL displayed in the terminal after the application starts.

## Project Structure

- `Pages/Index.razor` - Main sample page demonstrating the `SfUploader` component, file validation, local file saving, and file removal functionality.
- `Data/SampleDataController.cs` - ASP.NET Core Web API controller containing:
  - `Save()` method for uploading and storing files.
  - `Remove()` method for deleting uploaded files.
  - File existence validation and server-side file management logic.
- `Data/WeatherForecast.cs` - Default Blazor Server template model included with the project.
- `Data/WeatherForecastService.cs` - Default Blazor Server template service included with the project.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- Documentation: https://blazor.syncfusion.com/documentation/file-upload/getting-started

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.