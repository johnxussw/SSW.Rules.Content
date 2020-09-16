---
type: rule
archivedreason: 
title: Do you have good TypeScript configuration?
guid: 50191d0e-0e68-49ce-b324-53ee11aad6f7
uri: do-you-have-good-typescript-configuration
created: 2016-03-30T19:14:50.0000000Z
authors:
- id: 24
  title: Adam Stephensen
related: []

---

TypeScript is a powerful language that transpiles to JavaScript, and provides much desired type-safety and IDE refactoring support.  But without good configuration, a lot of the benefits can be lost.

<!--endintro-->

### Use tsconfig.json

Putting a “tsconfig.json” file in your project tells the typescript compiler where the root of your project is, and provides a centralized place to configure the compiler.  This config is read by IDEs and the compiler and can be utilised by the build scripts to ensure configuration is consistent.
<dl class="image">&lt;dt&gt; <img src="goodtypescriptconfig1.png" alt="goodtypescriptconfig1.png"> &lt;/dt&gt;<dd>Figure: A tsconfig.json file with great configuration</dd></dl>
### Disable implicit “any”

The primary benefit of TypeScript is type-safety, and attempting to escape from the type-safety should be a conscientious decision by the developer.  So ensure that noImplicitAny is true, and keep your code type-aware and able to be refactored.

### Exclude external files

By default, the compiler will compile everything ending in .ts.  This means things inside node\_modules and even typings will be parsed and included.  Ensure you exclude these files to reduce your compile time and, more importantly, reduce your reported errors.

### Don’t rely on TypeScript for bundling

TypeScript should compile in-place, and a single file input should produce a single file output.  This reduces compile time, and puts bundling in the hands of a system that knows more about the modules – the module loader.

### Hide generated files from your IDE

Files generated from typescript get in the way – you don’t want to scroll through .d.ts, .js and .js.map files all the time.  So hide them in the IDE.
In VSCode this can be done via the “files.exclude” key in the settings.json file.  For a shared experience across the team, check this file into source control.
<dl class="image">&lt;dt&gt; <img src="goodtypescriptconfig2.png" alt="goodtypescriptconfig2.png"> &lt;/dt&gt;<dd>Figure: VSCode settings.json file that hides generated files </dd></dl>