# scala-common-test

**Repository**: https://github.com/aml-org/scala-common-test

## Release Process
**Does NOT follow the regular release process.**

## Release Position
- Released **outside the regular release line** (when needed)
- Check if new release is needed before starting main release line
- Used as **development dependency** by most projects

## Branch Structure
**No 'develop' branch** - uses feature branch workflow:
1. Work in feature branches
2. Create PR to merge to `master`
3. Master automatically publishes new patch version based on Jenkins run number

## Files & Locations

### Version File
- `build.sbt` - specifies dependencies and major/minor version of the project

### Dependencies
Likely depends on scala-common (typical pattern)

## Versioning
- Major/minor version specified in `build.sbt`
- Patch version is **automatic** based on Jenkins run number
- Each merge to master triggers automatic publish

## Release Steps

### Publishing New Version
1. Create feature branch: `git checkout master && git pull && git checkout -b feature/description`
2. Make changes
3. Update major/minor version in `build.sbt` if needed
4. Commit changes: `git commit -m "Description of changes"`
5. Push: `git push -u origin feature/description`
6. Create PR to merge into `master`
7. When PR is merged, Jenkins automatically publishes new patch version

### No Manual Versioning
- Patch version is controlled by Jenkins run number
- No need to manually set full version
- Just update major/minor in build.sbt when needed

## Dependencies Impact
After releasing scala-common-test:
- Most projects in the AMF ecosystem use this as a dev dependency
- Check which projects need the updated version

## Notes
- Does not need to follow the release times of the rest of the projects
- Released only when needed
- Automatic patch versioning on every master merge
- No RC or manual release process
- Used for testing across the AMF ecosystem
