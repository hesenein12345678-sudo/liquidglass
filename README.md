# Backdrop Catalog — GitHub Actions bundle

This repository intentionally keeps the Android source in `project.zip`.
The GitHub Actions workflow:

1. checks out the repository;
2. installs JDK 17;
3. installs Gradle 9.7.1;
4. extracts `project.zip` into `android-project/`;
5. builds `:app:assembleDebug`;
6. verifies the APK exists; and
7. uploads the APK as a workflow artifact.

Do not upload another ZIP inside `project.zip`.
