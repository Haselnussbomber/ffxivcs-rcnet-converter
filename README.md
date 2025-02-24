This is a small script to generate a ReClass.NET project for [FFXIVClientStructs](https://github.com/aers/FFXIVClientStructs).

How to use:

- Have [ReClass.NET](https://github.com/ReClassNET/ReClass.NET) with the [XivReClassPlugin](https://github.com/pohky/XivReClassPlugin) installed. You most likely need to build these yourself.
- Have [Deno](https://deno.com/) installed.
- Copy `ffxiv_structs.yml` and `data.yml` from https://github.com/aers/FFXIVClientStructs/tree/main/ida into this directory.
- Run `deno run --allow-read=data.yml,ffxiv_structs.yml,ffxiv.rcnet --allow-write=ffxiv.rcnet convert-to-rcnet.ts` (or `deno run -A convert-to-rcnet.ts` if you trust the script).
- Open the `ffxiv.rcnet` project in ReClass.NET! :)


Bonus:

- If you don't have the XivReClassPlugin, you can add the flag `--plugin=false` to the script to disable the conversion of the types AtkValue, StdDeque, StdList, StdVector and Utf8String.
- If you want VTables, you can pass `--vtables` to the script.
