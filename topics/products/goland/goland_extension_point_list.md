# GoLand Extension Point and Listener List

<show-structure for="chapter" depth="2"/>

<!-- Copyright 2000-2022 JetBrains s.r.o. and contributors. Use of this source code is governed by the Apache 2.0 license. -->

17 Extension Points (EP) and 6 Listeners for GoLand

See [](extension_point_list.md) for IntelliJ Platform.

<include from="snippets.md" element-id="ep_list_legend"/>

## GoLand

### GoLand - Listeners

| Topic | Listener |
|-------|----------|
| [GoLibrariesService#LIBRARIES_TOPIC](https://jb.gg/ipe/listeners?topics=com.goide.project.GoLibrariesService.LibrariesListener)  | `LibrariesListener` |
| [GoModuleSettings#BUILD_TARGET_TOPIC](https://jb.gg/ipe/listeners?topics=com.goide.project.GoModuleSettings.BuildTargetListener)  ![Project-Level][project-level] | `BuildTargetListener` |
| [GoModuleSettings#GO_SUPPORT_TOPIC](https://jb.gg/ipe/listeners?topics=com.goide.project.GoModuleSettings.GoSupportListener)  ![Project-Level][project-level] | `GoSupportListener` |
| [GoModuleSettings#VENDORING_TOPIC](https://jb.gg/ipe/listeners?topics=com.goide.project.GoModuleSettings.VendoringListener)  ![Project-Level][project-level] | `VendoringListener` |
| [GoProjectLifecycleListener#TOPIC](https://jb.gg/ipe/listeners?topics=com.goide.project.GoProjectLifecycleListener)  | `GoProjectLifecycleListener` |
| [VgoProjectSettings#VGO_INTEGRATION_TOPIC](https://jb.gg/ipe/listeners?topics=com.goide.vgo.configuration.VgoProjectSettings.IntegrationListener)  | `IntegrationListener` |

### goland.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [com.goide.dlv.positionConverterFactory](https://jb.gg/ipe?extensions=com.goide.dlv.positionConverterFactory) | `DlvPositionConverterFactory` |
| [com.goide.documentation.packageVersionProvider](https://jb.gg/ipe?extensions=com.goide.documentation.packageVersionProvider) | `GoDocumentationPackageVersionProvider` |
| [com.goide.execution.defaultTargetEnvironmentProvider](https://jb.gg/ipe?extensions=com.goide.execution.defaultTargetEnvironmentProvider) | `DefaultTargetEnvironmentProvider` |
| [com.goide.executorExtension](https://jb.gg/ipe?extensions=com.goide.executorExtension) | `GoExecutorExtension` |
| [com.goide.highlighting.errorAnnotatorSuppressor](https://jb.gg/ipe?extensions=com.goide.highlighting.errorAnnotatorSuppressor) | `GoErrorAnnotatorSuppressor` |
| [com.goide.importResolver](https://jb.gg/ipe?extensions=com.goide.importResolver) | `GoImportResolver` |
| [com.goide.importsFilter](https://jb.gg/ipe?extensions=com.goide.importsFilter) | `GoImportsFilter` |
| [com.goide.packageFactory](https://jb.gg/ipe?extensions=com.goide.packageFactory) | `GoPackageFactory` |
| [com.goide.runConfigurationExtension](https://jb.gg/ipe?extensions=com.goide.runConfigurationExtension) | `GoRunConfigurationExtension` |
| [com.goide.sdk.sdkVetoer](https://jb.gg/ipe?extensions=com.goide.sdk.sdkVetoer) | `GoBasedSdkVetoer` |
| [com.goide.sdk.targetSdkVersionProvider](https://jb.gg/ipe?extensions=com.goide.sdk.targetSdkVersionProvider) | `GoTargetSdkVersionProvider` |
| [com.goide.sdkProvider](https://jb.gg/ipe?extensions=com.goide.sdkProvider) | `GoSdkProvider` |
| [com.goide.support](https://jb.gg/ipe?extensions=com.goide.support) | `GoLangSupport` |

### openapi.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [com.goide.documentation.additionalDocumentationProvider](https://jb.gg/ipe?extensions=com.goide.documentation.additionalDocumentationProvider) | `GoAdditionalDocumentationProvider` |
| [com.goide.importPathsProvider](https://jb.gg/ipe?extensions=com.goide.importPathsProvider) | `GoImportPathsProvider` |
| [com.goide.imports.weigher](https://jb.gg/ipe?extensions=com.goide.imports.weigher) | `GoImportsWeigher` |
| [com.goide.rootsProvider](https://jb.gg/ipe?extensions=com.goide.rootsProvider) | `GoRootsProvider` |

[experimental]: https://img.shields.io/badge/-Experimental_API-red?style=flat-square
[internal]: https://img.shields.io/badge/-Internal_API-darkred?style=flat-square
[project-level]: https://img.shields.io/badge/-Project--Level-blue?style=flat-square
[non-dynamic]: https://img.shields.io/badge/-Non--Dynamic-orange?style=flat-square
[deprecated]: https://img.shields.io/badge/-Deprecated-lightgrey?style=flat-square
