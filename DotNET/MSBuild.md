# MSBuild

## Make Directory in Output Folder

```xml
<Target Name="MakeMyDir" AfterTargets="Build">
   <MakeDir Directories="$(OutDir)Database" />
</Target>
```
