This is a small script to generate a ReClass.NET project for FFXIVClientStructs.

How to use:

- Have [ReClass.NET](https://github.com/ReClassNET/ReClass.NET) with the [XivReClassPlugin](https://github.com/pohky/XivReClassPlugin) installed. You most likely need to build these yourself.
- Have [Deno](https://deno.com/) and the .NET SDK installed.
- Clone or download this repo.
- Clone or download [FFXIVClientStructs](https://github.com/aers/FFXIVClientStructs) and navigate into the directory.
- Clone or [download](https://github.com/xivdev/EXDSchema/archive/refs/heads/main.zip) the latest [ExdSchema](https://github.com/xivdev/EXDSchema)s and extract them.
- Run ExcelGenerator: `dotnet run --project ExcelGenerator\ExcelGenerator.csproj "C:\Program Files (x86)\SquareEnix\FINAL FANTASY XIV - A Realm Reborn" <path-to-schemas>` (adjust as necessary).
- Run CExporter: `dotnet run --project CExporter\CExporter.csproj`
- Copy `ffxiv_structs.yml` and `data.yml` from the ida directory next to `convert-to-rcnet.ts` of this repo.
- While you're here, run `deno run --allow-read=data.yml,ffxiv_structs.yml,ffxiv.rcnet --allow-write=ffxiv.rcnet convert-to-rcnet.ts` (or `deno run -A convert-to-rcnet.ts` if you trust the script).
- Open the `ffxiv.rcnet` project in ReClass.NET! :)


CLI Args:

- `--plugin[=true|false]` (default `true`): If you don't have the XivReClassPlugin, you can disable the conversion of the types AtkValue, StdDeque, StdList, StdVector and Utf8String.
- `--vtables[=true|false]` (default `false`): This will generate unions with the VTable, if available in the data.yml.
