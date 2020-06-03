# CI/CD in Unity

[&olt; back](../../README.md)

A list of ways to do CI/CD in Unity projects

## Support Table

| Service           | 🤖 | 🍎 | 🟦 | 🧍‍♀️ | 🌐 |
|-------------------|----|-----|----|----|----|
| Unity Cloud Build | ✔ | ✔   | ❌ | ✔  | ✔  |
| Azure DevOps      | ✔ | ✔   | ✔  | ✔  | ✔ |
| GitHub Actions    | ❕ | ✔   | ❌ | ✔  | ✔  |

**Legend**
* 🤖 Android
* 🍎 iOS
* 🟦 UWP (Windows / HoloLens)
* 🧍‍♀️ Standalone
* 🌐 WebGL

## Unity Cloud Build

Recommended as the default go-to - comes with Unity Teams Advanced subscription, easy to set up and use. Only downer is lack of UWP support.

See [Documentation](https://docs.unity3d.com/Manual/UnityCloudBuild.html)

## Azure DevOps

Good cross-platform support, though having to install Unity each time makes it slow

* [Build Tools](https://dinomite-studios.github.io/unity-azure-pipelines-tasks/)
* [Microsoft's documentation](https://github.com/microsoft/Azure-DevOps-YAML-for-Unity)

## GitHub Actions

* [Repository / Documentation](https://github.com/webbertakken/unity-actions)