# Bug Fixes and Improvements List for Anytype iOS

This document contains a comprehensive list of potential bug fixes and improvements that developers could implement in the Anytype iOS repository.

## Table of Contents
1. [Technical Debt & Refactoring](#technical-debt--refactoring)
2. [Code Quality & Best Practices](#code-quality--best-practices)
3. [Performance Optimizations](#performance-optimizations)
4. [Security Improvements](#security-improvements)
5. [Testing & Test Coverage](#testing--test-coverage)
6. [Documentation](#documentation)
7. [Accessibility](#accessibility)
8. [Modern Swift Features](#modern-swift-features)
9. [UI/UX Improvements](#uiux-improvements)
10. [Developer Experience](#developer-experience)

---

## Technical Debt & Refactoring

### TODO Items (62+ instances found)
Based on code analysis, there are 62+ TODO/FIXME comments in the codebase that need attention:

1. **Fix AnytypeText rendering issue**
   - File: `Modules/DesignKit/Sources/DesignKit/Components/AnytypeText.swift:42`
   - Issue: TODO: Fix

2. **Fix negative line spacing**
   - File: `Modules/DesignKit/Sources/DesignKit/Fonts/Helpers/OptionalLineSpacingModifier.swift:8`
   - Issue: Negative line spacing not working

3. **Delete active view ID from middleware model**
   - File: `Modules/Services/Sources/Models/Block/BlockContainer/Array+Dataview.swift:4`
   - Issue: TODO: Delete active view ID from middleware model

4. **Rename hash properties**
   - File: `Modules/Services/Sources/Models/Block/BlockContainer/Models+Events/BlockBookmark+Handle.swift:21,26`
   - Issue: TODO: Rename hash (2 instances)

5. **Remove deprecated account fields**
   - File: `Modules/ProtobufMessages/Sources/Protocol/Commands/Anytype_Rpc.Account.Create.swift:32,70`
   - Issue: TODO: Remove if not needed, GO-1926

6. **Migrate to iOS 18 async sequence features**
   - File: `Modules/AsyncTools/Sources/AsyncTools/ConvertDataStream.swift:9`
   - Issue: When minimum iOS is 18, add S.Failure == Never and remove eraseToAnyAsyncSequence

7. **Delete legacy DI for multiwindow support**
   - File: `Anytype/Sources/PresentationLayer/Assemblies/UIHelpersDI.swift:3`
   - Issue: TODO: Legacy DI. Delete it for support multiwindow

8. **Move editor-related code**
   - File: `Anytype/Sources/PresentationLayer/Common/Extensions/RelationValuesProtocol+PageCellTitle.swift:18,27`
   - Issue: TODO: Move to editor (2 instances)

9. **Delete AnytypePopup**
   - File: `Anytype/Sources/PresentationLayer/Common/UIKit/AnytypePopup/AnytypePopup.swift:8`
   - Issue: TODO: Delete it

10. **Migrate to PhotosPicker**
    - File: `Anytype/Sources/PresentationLayer/Common/SwiftUI/MediaPicker/MediaPickerView.swift:4`
    - Issue: TODO: Migrate to PhotosPicker

11. **Migrate to iOS 17 completion handler**
    - File: `Anytype/Sources/PresentationLayer/Common/SwiftUI/PulseAnimation.swift:18`
    - Issue: TODO: Migrate to completion from iOS 17

12. **Remove LegacyLoginView**
    - File: `Anytype/Sources/PresentationLayer/Common/Factories/AlertsFactory.swift:6`
    - Issue: TODO: Remove with LegacyLoginView

13. **Migrate from LegacySearchView (multiple instances)**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Set/Views/Popups/SearchView/SetPropertiesDetailsLocalSearchView.swift:13`
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Set/Views/Popups/Filters/Selection/List/SetFiltersContentViewBuilder.swift:58`
    - Issue: TODO: Migrate from LegacySearchView

14. **Refactor SetFiltersDateCoordinatorViewModel**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Set/Views/Popups/Filters/Date/Coordinator/SetFiltersDateCoordinatorViewModel.swift:14`
    - Issue: TODO: Needs refactoring

15. **Refactor SetDocumentProtocol**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Set/Models/SetDocumentProtocol.swift:20`
    - Issue: TODO: Refactor this

16. **Delete TextBlockViewModel**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/BlocksViews/Blocks/Text/Base/TextBlockViewModel.swift:5`
    - Issue: TODO: Delete it. Use document subscription in blocks

17. **Rollback bookmark handling**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/BlocksViews/Blocks/Bookmark/BlockBookmarkViewModel.swift:65`
    - Issue: TODO: Rollback

18. **Open toast inside module**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Assembly/Set/EditorSetModuleOutput.swift:31`
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Assembly/Page/EditorPageModuleOutput.swift:26`
    - Issue: TODO: Open toast inside module

19. **Refactoring templates**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Assembly/Page/EditorPageModuleOutput.swift:24`
    - Issue: TODO: Refactoring templates. Delete it

20. **Migrate EditorRouter to EditorPageCoordinator**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Assembly/Page/EditorPageModuleOutput.swift:28`
    - Issue: TODO: Migrate EditorRouter to EditorPageCoordinator and make output as MainActor

21. **Refactoring cursor mode with IOS-1317**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/AccessoryView/EditorAccessoryView/CursorModeView/CursorModeAccessoryView.swift:71`
    - Issue: TODO: Refactoring with IOS-1317

22. **Refactoring editor view controller**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/EditorPage/EditorPageViewState.swift:5`
    - Issue: TODO: Refactoring editor view controller

23. **Add animation to navigation**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/EditorPage/Utils/EditorBottomNavigationManager.swift:47`
    - Issue: TODO: Add animation?

24. **Support new rows without stars and deletion**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/EditorPage/Views/Settings/Properties/Views/ObjectFieldsView/ObjectPropertiesView.swift:143`
    - Issue: TODO: Support new rows without stars and deletion

25. **Use subscription for editor page**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/EditorPage/EditorPageViewModel.swift:121`
    - Issue: TODO: Use subscription when ready

26. **Add analytics to RemoteStorage**
    - File: `Anytype/Sources/PresentationLayer/SpaceSettings/RemoteStorage/RemoteStorageViewModel.swift:54`
    - Issue: TODO: Add analytics

27. **Refactor widget modules (4 instances)**
    - File: `Anytype/Sources/PresentationLayer/Modules/WidgetObjectList/Common/WidgetObjectListView.swift:4`
    - File: `Anytype/Sources/PresentationLayer/Modules/WidgetObjectList/Files/WidgetObjectListFilesManagerView.swift:4`
    - File: `Anytype/Sources/PresentationLayer/Modules/WidgetObjectList/Recent/WidgetObjectListRecentOpenView.swift:4`
    - File: `Anytype/Sources/PresentationLayer/Modules/WidgetObjectList/Recent/WidgetObjectListRecentEditView.swift:4`
    - File: `Anytype/Sources/PresentationLayer/Modules/WidgetObjectList/Favorites/WidgetObjectListFavoritesView.swift:4`
    - Issue: Make common module without model, refactoring modules

28. **Delete ListWidgetView header**
    - File: `Anytype/Sources/PresentationLayer/Modules/HomeWidgets/Widgets/List/Common/ListWidgetView.swift:68`
    - Issue: TODO: Delete this header with galleryWidget toggle

29. **Fix chat messages preview equality**
    - File: `Anytype/Sources/PresentationLayer/Modules/Chat/Services/ChatMessagesPreviewsStorage.swift:165`
    - Issue: TODO: change to full equality after MW fix

### Deprecated Code (30+ instances)

30. **Remove deprecated "layout" property usage**
    - File: `Modules/Services/Sources/Models/Details/BundledPropertyValueProvider+CustomProperties.swift:10`
    - Issue: Use "resolvedLayout"; "layout" is deprecated

31. **Update deprecated block link style**
    - File: `Modules/Services/Sources/Models/Block/BlockLinkConverter.swift:29`
    - Issue: style = .page is deprecated

32. **Remove deprecated protobuf event fields**
    - Multiple files in `Modules/ProtobufMessages/Sources/Protocol/`
    - Issue: Clean up deprecated source, message, and other fields marked as deprecated

33. **Remove deprecated workspace/space fields**
    - File: `Modules/ProtobufMessages/Sources/Protocol/Commands/Anytype_Rpc.Workspace.Create.swift:40`
    - Issue: Use spaceUxType instead

34. **Remove deprecated invite view fields**
    - File: `Modules/ProtobufMessages/Sources/Protocol/Commands/Anytype_Rpc.Space.InviteView.swift:58`
    - Issue: Use inviteType instead

35. **Remove deprecated chat creation**
    - File: `Modules/ProtobufMessages/Sources/Protocol/Commands/Anytype_Rpc.Workspace.Open.swift:29`
    - Issue: Chat will be created automatically if space is shared

### Large File Refactoring

36. **Split Error+Localization.swift (7,913 lines)**
    - File: `Modules/ProtobufMessages/Sources/Loc/Generated/Error+Localization.swift`
    - Issue: Extremely large file, consider splitting into smaller modules

37. **Split service+invocation.swift (3,077 lines)**
    - File: `Modules/ProtobufMessages/Sources/Generated/service+invocation.swift`
    - Issue: Very large generated file

38. **Split Anytype_Event.Block.Set.swift (3,033 lines)**
    - File: `Modules/ProtobufMessages/Sources/Protocol/Events/Anytype_Event.Block.Set.swift`
    - Issue: Very large file

39. **Split Strings.swift (2,501 lines)**
    - File: `Modules/Loc/Sources/Loc/Generated/Strings.swift`
    - Issue: Large generated strings file

40. **Refactor AnytypeAnalytics+Events.swift (1,753 lines)**
    - File: `Anytype/Sources/Analytics/AnytypeAnalytics/AnytypeAnalytics+Events.swift`
    - Issue: Large analytics file, consider splitting by feature

41. **Refactor EditorSetViewModel.swift (885 lines)**
    - File: `Anytype/Sources/PresentationLayer/TextEditor/Set/EditorSetViewModel.swift`
    - Issue: Large view model, consider extracting business logic

---

## Code Quality & Best Practices

### Error Handling

42. **Replace force unwraps with safe unwrapping**
    - Found in 949 files with force unwrap operators (!)
    - Issue: Force unwraps can cause crashes, use optional binding or guard statements

43. **Replace `try!` with proper error handling**
    - Found 3 instances of `try!`
    - Issue: Replace with do-catch blocks or `try?` where appropriate

44. **Review fatalError usage**
    - File: `Modules/DesignKit/Sources/DesignKit/Fonts/Generated/Fonts.swift:73`
    - File: `Modules/DesignKit/Sources/DesignKit/Fonts/Config/UIKitFont.swift:161`
    - Issue: Replace fatalError with graceful fallbacks for font initialization

45. **Review preconditionFailure usage in generated code**
    - Found in multiple protobuf-generated files
    - Issue: Ensure proper handling of protobuf enum cases

### SwiftLint Violations

46. **Reduce swiftlint:disable directives (614 instances)**
    - Found 614 SwiftLint disable directives throughout codebase
    - Issue: Review and fix underlying issues instead of disabling rules

### Memory Management

47. **Review weak/unowned self usage (587 instances)**
    - Found 587 instances of weak/unowned self
    - Issue: Audit for potential retain cycles and ensure proper memory management

48. **Add missing [weak self] captures**
    - Review closures that capture self without weak reference
    - Issue: Potential memory leaks in async operations

### Logging & Debugging

49. **Replace print statements with logger**
    - File: `Modules/DesignKit/Sources/DesignKit/SystemExtensions/View+Extensions.swift`
    - Issue: Use structured logging instead of print()

---

## Performance Optimizations

50. **Optimize large view rendering**
    - Review SwiftUI views with complex hierarchies
    - Issue: Add lazy loading where appropriate

51. **Cache computed properties**
    - Review frequently accessed computed properties
    - Issue: Add caching for expensive computations

52. **Optimize image loading**
    - Review image loading and caching strategies
    - Issue: Implement proper image caching and lazy loading

53. **Reduce main thread blocking**
    - Found 818 instances of main thread operations
    - Issue: Move heavy operations off main thread

54. **Optimize data subscriptions**
    - Review subscription patterns
    - Issue: Ensure subscriptions are properly scoped and cleaned up

---

## Security Improvements

55. **Audit sensitive data handling**
    - Review SecureService module
    - Issue: Ensure proper encryption and secure storage

56. **Review keychain usage**
    - Audit keychain operations
    - Issue: Ensure proper keychain access control

57. **Add input validation**
    - Review user input handling
    - Issue: Add validation and sanitization

58. **Review network security**
    - Audit network requests
    - Issue: Ensure HTTPS, certificate pinning where appropriate

---

## Testing & Test Coverage

59. **Increase test coverage (only 13 test files found)**
    - Current: 13 test files vs 3,003 source files
    - Issue: Add unit tests for business logic, view models, and services

60. **Add UI tests**
    - No UI test files found
    - Issue: Add UI tests for critical user flows

61. **Add snapshot tests**
    - No snapshot testing infrastructure found
    - Issue: Add snapshot tests for UI components

62. **Add integration tests**
    - Issue: Add tests for middleware integration

63. **Add performance tests**
    - Issue: Add performance benchmarks for critical operations

64. **Mock middleware responses**
    - Issue: Create comprehensive mocks for testing

---

## Documentation

65. **Add missing code documentation**
    - Many public APIs lack documentation
    - Issue: Add Swift documentation comments (///)

66. **Update README with build instructions**
    - Current README is basic
    - Issue: Add detailed setup, troubleshooting, and contribution guidelines

67. **Document architecture patterns**
    - Issue: Add architecture decision records (ADRs)

68. **Add inline code examples**
    - Issue: Add examples for complex APIs

69. **Create API documentation**
    - Issue: Generate and publish API documentation

70. **Document middleware protocol**
    - Issue: Document anytype-heart integration points

---

## Accessibility

71. **Add VoiceOver support**
    - Review accessibility labels and hints
    - Issue: Add comprehensive VoiceOver support

72. **Add Dynamic Type support**
    - Review font scaling
    - Issue: Ensure all text supports Dynamic Type

73. **Improve color contrast**
    - Review color system
    - Issue: Ensure WCAG compliance

74. **Add accessibility identifiers**
    - For UI testing and automation
    - Issue: Add consistent identifiers

75. **Support accessibility actions**
    - Issue: Add custom accessibility actions for complex views

---

## Modern Swift Features

76. **Migrate to Swift Concurrency**
    - Found legacy async patterns
    - Issue: Replace completion handlers with async/await

77. **Use @MainActor consistently**
    - Review main actor usage
    - Issue: Annotate UI code with @MainActor

78. **Adopt Swift 5.9+ features**
    - Issue: Use macros, parameter packs where beneficial

79. **Replace ObservableObject with @Observable**
    - Found 914+ instances of ObservableObject/@Published
    - Issue: Migrate to new Observation framework (iOS 17+)

80. **Use if let shorthand**
    - Issue: Modernize optional binding syntax

81. **Use type inference**
    - Issue: Simplify verbose type annotations

---

## UI/UX Improvements

82. **Remove legacy storyboards**
    - Found 2 storyboard files
    - File: `AnytypeShareExtension/Base.lproj/MainInterface.storyboard`
    - File: `Anytype/Supporting files/Base.lproj/LaunchScreen.storyboard`
    - Issue: Migrate to SwiftUI/programmatic UI

83. **Migrate UIKit to SwiftUI**
    - Found 14 UIViewController/UIView classes
    - Issue: Continue SwiftUI migration for consistency

84. **Improve animation consistency**
    - Issue: Standardize animation curves and durations

85. **Add loading states**
    - Issue: Improve loading indicators and skeleton screens

86. **Improve error messages**
    - Issue: Make error messages more user-friendly

87. **Add haptic feedback**
    - Issue: Add appropriate haptic feedback for actions

---

## Developer Experience

88. **Add SwiftLint configuration**
    - No `.swiftlint.yml` found
    - Issue: Add SwiftLint with custom rules

89. **Add pre-commit hooks**
    - Has `.pre-commit-config.yaml`
    - Issue: Ensure hooks are comprehensive and documented

90. **Improve build times**
    - Issue: Analyze and optimize module dependencies

91. **Add code generation documentation**
    - Has `CODE_GENERATION_GUIDE.md`
    - Issue: Ensure it's up to date and comprehensive

92. **Improve CI/CD pipeline**
    - Review GitHub Actions workflows
    - Issue: Add more checks (security scanning, complexity analysis)

93. **Add danger bot**
    - Issue: Automate PR review comments

94. **Improve module organization**
    - 17 Swift packages found
    - Issue: Review and optimize module dependencies

95. **Add debugging helpers**
    - Issue: Add more debug logging and diagnostic tools

96. **Improve dependency management**
    - Issue: Audit and update dependencies regularly

97. **Add automated changelog**
    - Issue: Generate changelogs from commits/PRs

---

## Localization

98. **Improve localization coverage**
    - Found 340 localization instances
    - Issue: Audit for missing translations

99. **Add RTL language support**
    - Issue: Test and improve right-to-left language support

100. **Extract hardcoded strings**
     - Issue: Find and localize any hardcoded user-facing strings

---

## Middleware Integration

101. **Update middleware version management**
     - Has Libraryfile for version tracking
     - Issue: Automate middleware version updates

102. **Improve middleware error handling**
     - Issue: Better error messages from middleware failures

103. **Add middleware telemetry**
     - Issue: Track middleware performance and errors

104. **Document middleware protocol changes**
     - Issue: Maintain changelog for protocol updates

---

## Infrastructure

105. **Add crash reporting integration**
     - Issue: Ensure comprehensive crash reporting

106. **Add analytics verification**
     - Issue: Validate analytics events are firing correctly

107. **Improve app startup time**
     - Issue: Profile and optimize launch sequence

108. **Add background task optimization**
     - Issue: Optimize background sync and processing

109. **Improve battery efficiency**
     - Issue: Profile and reduce battery impact

110. **Add network request retry logic**
     - Issue: Implement exponential backoff for failed requests

---

## Code Organization

111. **Standardize file naming**
     - Issue: Ensure consistent naming conventions

112. **Organize imports**
     - Found 1624 Foundation, 922 SwiftUI, 459 UIKit imports
     - Issue: Remove unused imports, organize systematically

113. **Reduce code duplication**
     - Issue: Extract common patterns into utilities

114. **Improve MARK usage**
     - Issue: Consistent use of // MARK: comments for organization

115. **Add file headers**
     - Issue: Standardize file header format with copyright

---

## Additional Improvements

116. **Add feature flags system**
     - Issue: Implement feature toggles for gradual rollouts

117. **Improve onboarding**
     - Issue: Better first-time user experience

118. **Add app shortcuts**
     - Issue: iOS app shortcuts for common actions

119. **Add Spotlight integration**
     - Issue: Make content searchable via Spotlight

120. **Add Handoff support**
     - Issue: Enable continuity between devices

121. **Improve share extension**
     - Issue: Enhance content sharing capabilities

122. **Add widget improvements**
     - Issue: More widget types and configurations

123. **Improve notification handling**
     - Issue: Better notification UI and actions

124. **Add today extension alternatives**
     - Issue: Modern widget alternatives

125. **Implement proper deep linking**
     - DeepLinks module exists
     - Issue: Ensure comprehensive deep link support

---

## Priority Recommendations

### High Priority (Should address soon)
- Fix force unwraps (42) and try! statements (43)
- Increase test coverage (59-64)
- Migrate from deprecated APIs (30-35)
- Address TODO items with security/stability impact (1-29)
- Add SwiftLint configuration (88)

### Medium Priority (Nice to have)
- Refactor large files (36-41)
- Improve documentation (65-70)
- Enhance accessibility (71-75)
- Modernize Swift usage (76-81)

### Low Priority (Future enhancements)
- UI/UX polish (82-87)
- Additional features (116-125)
- Performance optimizations (50-54)

---

## How to Contribute

1. Pick an item from this list
2. Create a GitHub issue if one doesn't exist
3. Assign yourself and update the issue with your plan
4. Create a PR with focused, well-tested changes
5. Update this document when items are completed

## Notes

- This list was generated through automated code analysis
- Some items may already be in progress or completed
- Priority and feasibility should be evaluated before implementation
- Generated on: 2025-11-14
- Total items identified: 125+

---

*This is a living document. Please update as items are addressed or new issues are discovered.*
