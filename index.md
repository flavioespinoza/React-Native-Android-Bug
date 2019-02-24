# React Native 🐞 'run-android' bug

<header class='md-header'>

### Overview

</header>

- **github:**  <a  class='md-link' 
                    target='_blank'
                    href='https://github.com/facebook/react-native'>
                    react-native
                </a>

- **bug: 🐞** Perpetual build failures during the "react-native  run-android" even with no code changes 

- **high-level theory:**  

    <div class='md-theory'>

    **Xcode build sequence** is breaking a process in the **react-native  run-android** when developing on **macOS**
        
    </div>

<div class='md-label-header'>

<header class='md-header'>

### Approach

</header>

**Observations**

</div>

> Add the following to 
    <a  class='md-link-bold' 
        target='_blank' 
        href='observations.html'>
        Observations
    </a>
    ~ Then proceed to **Stategy** section below
    

- [ ] Detailed observations on sequencing and the app-server
- [ ] Erorr logs and stack-traces from dev environment
- [ ] Bug 🐞 reports on [react-native/issues](https://github.com/facebook/react-native/issues)
- [ ] Bug 🐞 reports on [Stack Overflow](https://stackoverflow.com/search?q=macos+react-native+run-android+build+failure)
- [ ] Thoughts on how the iOS Xcode requirement on might be breaking or delaying the Android build_
- [ ] Detailed description of a workaround on the Android side and reasoning on how it might be solve_ 

<div class='md-label-header'>

**Strategy**

</div>

> Separate the Android and iOS app-servers to run separate virtual machines

<div class='md-label-header md-label-header-todo'>

**Todo**

</div>

- [ ] Gain deeper understanding of the 
        <a class='md-link-bold' target='_blank' href='https://developer.apple.com/videos/play/wwdc2018/415/'>
            Xcode build sequence
        </a>
- [ ] Test **Trident strategy** outlined below
- [ ] Asses **Trident strategy** and proceed based on resluts
- [ ] _Add todo...continue..._


<div class='md-label-header md-label-header-strategy'>

**Trident strategy**

</div>

<div class='md-strategy'>

> First iteration

</div>

- [ ] Use react-native-cli to create three parojects 

    - androidApp
    - iosApp
    - tridentApp

- [ ] Remove `ios` folders from the **androidApp**
- [ ] Remove `android` folders from the **iosApp**
- [ ] Remove `android` and `ios` folders from the **tridentApp**

- [ ] Open the .watchmanconfig file in the **tridentApp**
- [ ] Change the default output configs to watch the **androidApp** to watch for changes in the  **tridentApp** and output to its root `android` folder

- [ ] Test if it works and proceed accordingly
- [ ] _Add todo...continue..._
