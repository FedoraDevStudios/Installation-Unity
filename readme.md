# Installation

My projects use [Odin Inspector](https://assetstore.unity.com/packages/tools/utilities/odin-inspector-and-serializer-89041), which I cannot redistribute. If you don't own Odin Inspector, I would highly recommend purchasing it otherwise you won't be able to serialize interface instances as members which completely breaks my packages.

If the package has any additional requirements, be sure to add them as well.

#### Package Manager
##### Git Extension
First, do yourself a favor and add the [UPM Git Extension](https://github.com/mob-sakai/UpmGitExtension) package to your project. This package makes git packages many times easier to use in your project. simply add `https://github.com/mob-sakai/UpmGitExtension.git` as a new package via the git option in the package manager. Afterwords, reopen the Package Manager.

Next, add this repo. In the top left, you will find a git logo. This button will show a small menu for adding git packages to your project. add `https://github.com/FedoraDevStudios/[Package-Name].git` in the `Repository URL` box and hit `Find Versions`. Select the latest version and then `Install Package`.

#### UPM Upgrade
If you added the Git Extension package, then you can change the installed version just like any other package.

#### Manual Installation
This can be added as a dependency to your Unity project manually. You just need to add a reference to this repo to your project's `Packages/manifest.json` file. Be sure to switch `[version]` with whichever release you would prefer, e.g. `.git#1.0.0`.

```js
{
	"dependencies": {
		...,
		"com.fedoradev.[packagename]": "https://github.com/FedoraDevStudios/[Package-Name].git#[version]"
	}
}
```

#### Manual Upgrade
After installing manually, you have to change both `Packages/manifest.json` and `Packages/packages-lock.json`. In the former, simply update the dependency with the version you wish to pull. In the lock file, you need to remove the entry for the package. This entry is a few lines long and everything needs to be deleted, including the curly braces. After this is successfully completed, moving back to Unity will force the application to download the desired version.