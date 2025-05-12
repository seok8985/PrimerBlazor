
## 🚀 Getting Started

PrimerBlazor is available for free on [NuGet](https://www.nuget.org/packages/PrimerBlazor), and the demo-related source code is open-source on [GitHub](https://github.com/seok8985/PrimerBlazor).

### ✅ Install via NuGet (.NET 8+)

Install the package using the NuGet CLI:

```bash
dotnet add package PrimerBlazor
```

### 🎨 Import Global Styles

Add the following to your `wwwroot/index.html` (Blazor WebAssembly) or `_Host.cshtml` (Blazor Server):

```html
<link href="_content/PrimerBlazor/css/style.css" rel="stylesheet" />
```

### 🔌 Register JS Interop

The JavaScript file `primerBlazorJsInterop.js` is automatically included by the `PrimerBlazor` package.

### 🌐 Blazor Web App (.NET 9+) Notes

When using PrimerBlazor in a **.NET 9+ Blazor Web App**, JavaScript modules are automatically registered using the built-in `<script type="importmap">` mechanism.

You **do not** need to manually add the script reference for `primerBlazorJsInterop.js`:

```html
<script type="importmap">{
  "imports": {
    "./_content/PrimerBlazor/js/primerBlazorJsInterop.js": "./_content/PrimerBlazor/js/primerBlazorJsInterop.wxyz1234.js"
  }
}</script>
```

However, **CSS files are not included** in the import map and must still be linked manually:

```html
<link href="_content/PrimerBlazor/css/style.css" rel="stylesheet" />
```

Also, register the interop service in `Program.cs` to enable clipboard and dynamic UI behaviors:

```csharp
builder.Services.AddScoped<PrimerBlazorJsInterop>();
```

### 📄 Add Imports

Include this line in your `_Imports.razor` file:

```razor
@using PrimerBlazor
```

### 🧩 Start Using Components

You can now use components like `<PrimerBrandButton />`, `<PrimerBrandStack />`, and more.

