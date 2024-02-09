# MSBuild

## Make Directory in Output Folder

```xml
<Target Name="<TargetName>" AfterTargets="Build">
   <MakeDir Directories="$(OutDir)<DirectoryName>" />
</Target>
```
