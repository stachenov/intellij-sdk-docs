# Plugin User Experience (UX)

<!-- Copyright 2000-2022 JetBrains s.r.o. and contributors. Use of this source code is governed by the Apache 2.0 license. -->

_User Experience (UX)_ is a term describing the experience users feel when using a product.
It covers not only aspects like visual presentation, performance, stability, or ease of use, but anything that affects the user's satisfaction.
It's an overall impression of using a product that strongly indicates whether a user likes it or not.

IntelliJ Platform-based plugins are products, and providing a good UX is very important for retaining users and making them recommend your plugin to others.
A bad plugin UX can negatively impact the user base, as users tend to abandon plugins that bring frustration, e.g., by instability, poor performance, or complexity.

The following sections explain the selected plugin UX areas.

## General Advice

Great IntelliJ Platform plugins, like any other products, should bring significant value to users.
When planning your work, talk and try to understand what your users need the most and prioritize crucial functionalities.

If you are unsure about an implemented solution, consider sharing the work in progress with a limited group of users (e.g., your colleagues or active community members) and gathering the feedback that will help you improve the final result.
See the [Custom Release Channels](publishing_plugin.md#specifying-a-release-channel) section for information on how to automate sharing the pre-release plugin versions.

Gathering feedback for the existing features can help identify what works well and what should be improved, which also increases the overall plugin quality.

## Ease of Use

Plugins should be just easy to use.
Ideally, all the features should work out of the box after the installation, without any special user interactions, like manually enabling crucial plugin features.
Default settings should reflect the typical plugin usage in a standard project.

All the settings and actions should be easy to find and be placed in the proper [settings](settings.md) or [action group](grouping_action.md), e.g.:
* framework plugin settings should be placed under the <ui-path>Settings/Preferences | Languages & Frameworks</ui-path>
* action marking a directory as a plugin-specific root should be added to <ui-path>Mark Directory as...</ui-path> group

Plugins that are hard to configure with features that are hard to find may be quickly abandoned out of frustration.

## Stability

Plugins that throw a lot of errors visible in the messages panel and execute actions resulting in incorrect behavior, e.g., generating incorrect code, are considered unstable and unreliable.

To improve the overall stability and minimize the risk of introducing regression issues, it is critical to implement [functional tests](testing_plugins.md) with a low maintenance cost.
It is a great safety net, which in the long term, will speed up your development and help you release new versions without the fear of breaking existing plugin features.

It's nearly impossible to develop software without bugs, so it is recommended to set up an issue tracker where users can report errors.
In addition, it's worth implementing a custom [error report submitter](ide_infrastructure.md#error-reporting) that allows sending error reports directly from within the IDE, with all required information attached.

## Performance

Even if a plugin works correctly and looks pleasing, poor performance will impact user satisfaction.
Slow highlighting, code completion, code generation, and other features may break the user's workflow and cause frustration leading to plugin uninstallation.
Always try to follow the performance tips described on the topic pages, e.g.:
* [](psi_performance.md)
* [](general_threading_rules.md#avoiding-ui-freezes)
* [](indexing_and_psi_stubs.md#improving-indexing-performance)

## Distribution Size

In addition to the plugin execution performance, it is recommended to optimize the size of the plugin distribution that is downloaded by users from JetBrains Marketplace.
Users with a poor internet connection may cancel the download when they realize that it will take too long to wait for a plugin they are not sure will meet their expectations.
Consider the following techniques for optimizing the plugin distribution size:
* Decrease the number of dependencies. Check if the target platform includes utilities or libraries you need and reuse them by declaring runtime dependency if needed.
* Optimize assets like images, videos, etc.
* If large resources (e.g., SDKs) will be needed only in specific setups, consider downloading them by the plugin on-demand instead of bundling them in the plugin distribution.

## Consistent Behavior

When designing and implementing features, review existing functionalities of the IDE and plugins and design your features in a similar and consistent way.
A consistent approach will make it easier for users to work with your plugin, increasing overall satisfaction.

If you implement custom language support, review and consider implementing extension points from the [](additional_minor_features.md) list so that your plugin provides an experience consistent with other plugins.

## Consistent and Good-Looking UI

If a plugin UI significantly differs from the other application parts, it can feel alien to people and might be considered low quality or neglected.
Review and follow the rules described in the [IntelliJ Platform UI Guidelines](https://jetbrains.design/intellij/).
Pay attention to [icons](https://jetbrains.design/intellij/principles/icons/) and make them match the IDE style.
Use the UI controls recommended for a given use case.
Use [UI Inspector](internal_ui_inspector.md) to see how the existing UI is implemented.

## High-Quality Texts

Bad-quality labels or texts with typos and grammatical errors make a bad impression.
All the UI texts should follow the rules described in the _Text_ section of the [IntelliJ Platform UI Guidelines](https://jetbrains.design/intellij/).
It is recommended to proofread the texts or use one of the [spellcheck plugins](https://plugins.jetbrains.com/search?tags=Spellcheck).

## Plugin Description and Presentation

Description on the plugin page is the place where users have the first contact with the plugin, and its content helps them to decide if it is what they are looking for.
The description should be clear, polished, and follow the rules described in the JetBrains Marketplace [documentation](https://plugins.jetbrains.com/docs/marketplace/plugin-overview-page.html#plugin-description).
See also the "[5 tips for optimizing the JetBrains Marketplace plugin page](https://youtu.be/oB1GA9JeeiY?t=52)".
