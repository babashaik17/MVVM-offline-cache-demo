# MVVM-offline-cache-demo:

The goal of this app is to build an app that shows the current trending Github
repositories fetched from a public API. The design and business specifications have been
provided below. We expect you to follow it as closely as possible.

The application consists of three screens. The home screen where you search and display
a list of repositories. Repo Details screen where you list the necessary information about the
repository. Contributors screen where his/her details and list of repositories are mentioned.
Necessary information is listed below.

**Home:**
```
· A search bar to search from git API's
· A recycler view using card view to display the search results.
· The results are sorted in the descending order of the "watchers" count.
· The results count should be limited to 10.
· Clicking on an item to go to Repo Details Activity
· Dynamic Filters have to be implemented on the results displayed.
· Implementation/Use-case of the filter is up to your imagination.
```

**Repo Details:**
```
· This Activity should have a detailed description of the selected item.
· Details such as Image, Name, Project Link, Description, Contributors should be
displayed.
· When clicked on project link the URL should be opened in an In-app Browser(Web
View)
· When clicked on a contributor it should go to Contributor Details
```

**Contributor Details:**
```
· This Activity should have a detailed description of the contributor.
· Details such as Contributor Avatar(image),RepoList.
· Recycler view with card view should be used to display the repo list.
· Clicking on an item from the repo list it should display the detailed description of the
repo in a new Activity (Repo Details).
```

**API Details:**
```
The complete API docs are available:​ ​https://developer.github.com/v3/search/
```

# Application Architecture
![alt text](https://cdn-images-1.medium.com/max/1600/1*OqeNRtyjgWZzeUifrQT-NA.png)

The main advatage of using MVVM, there is no two way dependency between ViewModel and Model unlike MVP. Here the view can observe the datachanges in the viewmodel as we are using LiveData which is lifecycle aware. The viewmodel to view communication is achieved through observer pattern (basically observing the state changes of the data in the viewmodel).

## Dev Environment
* Kotlin V 1.3 +
* Java 8 Compatibility
* Min SDk Support 18
* Target SDK 29
* Android Studio 3.5 +

### Libraries uses
- Android Architecture Component (View model, Live data, Lifecycle
  aware, Navigation Component)
- Retrofit with OkHTTP3 (with 2 hrs offline API caching)
- Stetho for debugging
- Glide
- Dagger2
- Shimmer
- Realm (For full offline support, was not part of initial requirement but implemented for demo purpose)
- Google gson

### License
```
   Copyright (C) 2019-2020 JINESH SONI

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```

