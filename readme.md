This is a showcase of a pure metapackage for Microsoft.Extensions.Logging for different target frameworks.

Pure metapackage is a package that includes only a dependency list.

We however wish to enforce the following behavior:
* Metapackage A depends on packages P1 and P2.
* Shared Library SL depends on metapackage A.
* SL is packaged as nuget.
* SL has packages P1 and P2 marked as dependencies, however, no package A.

This behavior is to not confuse our partners with unknown metapackages A and instead expose the well-known packages P1 and P2.

This can come handy when we want to combine versions of packages that work with different targets. Microsoft.Extensions.Logging is a great example.



Intended consumption of the package within csproj is:
```
    <ItemGroup>
		<PackageReference Include="Microsoft.IC3.Extensions.Logging" Version="1.0.0.7">
		  <PrivateAssets>all</PrivateAssets>
		</PackageReference>
    </ItemGroup>
```