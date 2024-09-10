# MSBuild

## SDK Style Projects

The SDK style import:

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <!-- ... -->
</Project>
```

is equivalent to explicit imports:

```xml
<Project>
    <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
        <!-- ... -->
    <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

## Embedding Resources

```xml
<ItemGroup>
    <EmbeddedResource Include="assets/**/*" />
</ItemGroup>
```

## Copy Files to Output Folder

```xml
<ItemGroup>
    <Content Include="./assets/**/*.*">
        <Link>assets\%(RecursiveDir)%(Filename)%(Extension)</Link>
        <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
    </Content>
</ItemGroup>
```

## Make Directory in Output Folder

```xml
<Target Name="<TargetName>" AfterTargets="Build">
   <MakeDir Directories="$(OutDir)<DirectoryName>" />
</Target>
```

## Assembly References
```xml
<ItemGroup >
    <Reference Include="AssemblyName">
        <HintPath>..path..\AssemblyName.dll</HintPath>
        <!-- By setting <Private>False</Private> the DLLs won't be copied to the output folder (they may be loaded elsewhere) -->
        <Private>False</Private>
    </Reference>
</ItemGroup>
```
