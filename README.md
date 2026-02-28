# Project 1 - *Scavenger Hunt*

Submitted by: **Alec Rivera**

**Scavenger Hunt** is an app that challenges users to complete a list of photo-based tasks. Each task requires the user to attach a photo as proof of completion. Once a photo is attached, the app marks the task as complete and displays a map showing exactly where the photo was taken.

Time spent: **4** hours spent in total

## Required Features

The following **required** functionality is completed:

- [x] App displays list of hard-coded tasks
- [x] When a task is tapped it navigates the user to a task detail view
- [x] When user adds photo to complete the tasks, it marks the task as complete
- [x] When adding photo of task, the location is added
- [x] User returns to home page (list of tasks) and the status of your task is updated to complete

The following **optional** features are implemented:

- [ ] User can launch camera to snap a picture	

The following **additional** features are implemented:

- [x] Custom map annotation view displays the attached photo as the map pin
- [x] Progress counter in the navigation bar shows how many tasks are completed (e.g. 2/8)
- [x] "View Photo" button on the task detail screen opens a full-screen photo viewer
- [x] Tasks that are complete show a thumbnail of the attached photo in the task list
- [x] If a photo has no location metadata, the app shows a friendly warning instead of crashing
- [x] Alert with "Go to Settings" shortcut shown if photo library access is denied

## Video Walkthrough

https://www.loom.com/share/4b4e8f606e104fafaa0129b964e08b67
## Notes

Some challenges encountered while building the app:

- Getting location metadata from photos requires the user to grant **Full Access** (not just "Limited Access") to the photo library. PHPicker's `assetIdentifier` only works with full access, so the authorization flow had to explicitly request `.readWrite` access.
- The `NSPhotoLibraryUsageDescription` privacy key needed to be added to **both** the Debug and Release build configurations in the project settings. Since the project uses `GENERATE_INFOPLIST_FILE = YES`, there is no separate Info.plist file — the keys must be set as `INFOPLIST_KEY_*` build settings, and they must exist in every configuration or the app crashes on Debug builds.
- Swift's built-in `Task` concurrency type conflicts with a custom class also named `Task`. This was resolved by renaming the data model carefully and importing `Combine` explicitly for `@Published` and `ObservableObject` to work.

## License

    Copyright 2026 Alec Rivera

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
