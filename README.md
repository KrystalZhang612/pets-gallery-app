# PetsGallery App
A SwiftUI video-based application with AVPlayer and the Pexels API that is full of various cute pets videos in 5 categories. The App contains different components and views, with JSON data, JSON data conversion into a custom SwiftUI model, API is called asynchronously, and also uses AVPlayer (from AVKit) to integrate the media player. I built this App for my crush Jason Yu as his birthday gift. 
## ***[Copyright and Commercial Use Disclaimer](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/README.md#please-carefully-read-licensemd-about-the-open-source-restrictions-and-the-personal-use-policy-of-this-project-under-gpl-30-license-any-commericial-uses-on-this-project-by-other-than-the-owner-krystalzhang612-or-the-authorized-users-and-organizations-will-be-subjected-to-copyright-violation-with-sebsequent-potential-legal-concerns)***

⏬

### ***Please carefully read [LICENSE.md](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/LICENSE) about the Open Source restrictions and the personal use policy of this project under [GPL-3.0 license](https://www.gnu.org/licenses/gpl-3.0.en.html), any commericial uses on this project by other than the owner [@KrystalZhang612](https://github.com/KrystalZhang612) or the authorized users and organizations will be subjected to copyright violation with sebsequent potential legal concerns.***
## PetsGallery App Overview:
<p align = "center">
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/PetsGallery%20App%20Overview1.PNG" width = "380" height = "848.81818"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/PetsGallery%20App%20Overview2.PNG" width = "380" height = "848.81818"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/PetsGallery%20App%20Overview3.PNG" width = "380" height = "848.81818"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/PetsGallery%20App%20Overview4.PNG"  width = "380" height = "848.81818"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/PetsGallery%20App%20Overview5.PNG" width = "380" height = "848.81818"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/PetsGallery%20App%20Overview6.PNG"  width = "380" height = "848.81818"/>&nbsp;
</p>

# Build
[Method to Run & Test the Project Locally](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/README.md#method-to-run--test-the-project-locally)<br/> 
[Synchronous Developing Notes](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/README.md#synchronous-developing-notes)<br/> 
[Testing Result](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/README.md#testing-result)<br/> 
[Tags and Topics](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/README.md#tags-and-topics)<br/> 
# Contribution
[Author]()
# Compatibility
|   OS             | Supported          |
| -------          | ------------------ |
| iOS 15+          | :white_check_mark: |
| < iOS 15         | :x:                |
| macOS Mojave     | ✅                 |
| macOS Monterey   | ✅                 |
# Method to Run & Test the Project Locally
### Download the entire project to local directory
### Xcode must be `13.4` and higher versions with all Xcode dependencies updated.
### Compatible with `MacOS Monterey 12.0` or higher versions
### Run the project, choose Simulator iPhone 14 or iPhone 14 Pro Max with `iOS15+` for best compatiability.
# 🛠️ Developing Languages, Tools, and Techniques Needed
[Xcode Version 14.1](https://developer.apple.com/xcode/)<br/> 
[Swift 5.7](https://docs.swift.org/swift-book/)<br/> 
[SwiftUI](https://developer.apple.com/xcode/swiftui/)<br/>
[Pexels API](https://www.pexels.com/api)<br/> 
[JSON API](https://designcode.io/swiftui-advanced-handbook-data-from-json)<br/> 
[AVKit](https://developer.apple.com/documentation/avkit)<br/> 
<div>
 <img src = "https://github.com/devicons/devicon/blob/master/icons/xcode/xcode-original.svg" width = "60" height = "60" title = "Xcode"/>&nbsp; 
 <img src = "https://github.com/devicons/devicon/blob/master/icons/swift/swift-original.svg" width = "60" height = "60" title = "Swift"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/images-attachments-collection/blob/main/swift%20ui%20symbol%20logo.png"  width = "60" height = "60" title = "SwiftUI"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/images-attachments-collection/blob/main/pexels%20logo.png" width = "60" height = "60" title = "pexels"/>&nbsp; 
 <img src = "https://github.com/KrystalZhang612/images-attachments-collection/blob/main/JSON%20logo.png" width = "60" height = "60" title = "JSON"/>&nbsp;  
</div>

# Synchronous Developing Notes
## ***Create Query Tag***
Code query tag in [QueryTag.swift](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/PetsGalleryApp/Components/QueryTag.swift):
```swift 
var isSelected: Bool
var body: some View {
        Text(query)
            .font(.caption)
            .bold()
            .foregroundColor(isSelected ? .black : .gray)
            .padding(10)
            .background(.thinMaterial)
            .cornerRadius(10)
```
Make categories visible in [ContentView.swift](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/PetsGalleryApp/Views/ContentView.swift):
```swift 
struct ContentView: View {
    var body: some View {
        VStack {
            HStack {
                ForEach(Query.allCases, id: \.self){
                    searchQuery in
                    QueryTag(query: searchQuery, isSelected: false)
                }
```
[all categories showed.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/all%20categories%20showed.PNG)<br/>
## ***Customize Video cards***
Create a new SwiftUI file [VideoCard.swift](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/PetsGalleryApp/Components/VideoCard.swift):
```swift
 ZStack(alignment: .bottomLeading){
            AsyncImage(url: URL(string: "")) { image in
                image.resizable()
                    .aspectRatio(contentMode: .fill)
                    .frame(width: 160, height: 250)
            } placeholder: {
                Rectangle()
                    .foregroundColor(.gray.opacity(0.3))
        
.frame(width: 160, height: 250)
```
[video card initial frame.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20card%20initial%20frame.PNG)<br/>
Import video play button:
```swift
 Image(systemName: "play.fill")
                .foregroundColor(.white)
                .font(.title)
                .padding()
                .background(.ultraThinMaterial)
                .cornerRadius(50)
```
[video play button.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20play%20button.PNG)<br/>
## ***The Pexels API and ResponseBody model***
Based on pexel page, attach the needed attributes into [VideoManager.swift](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/PetsGalleryApp/VideoManager.swift):
```swift
struct ResponseBody: Decodable {
    var page: Int
    var perPage: Int
    var totalResults: Int
    var url: String
    var videos: [Video]
```
## ***Add JSON data***
Import [videoData.json](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/PetsGalleryApp/Preview%20Content/videoData.json) as preview content, and in VideoCard.swift:
```swift 
AsyncImage(url: URL(string: video.image))
```
[video cover image displayed.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20cover%20image%20displayed.PNG)<br/>
In [VideoView.swift](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/PetsGalleryApp/Views/VideoView.swift), add play button:
```swift 
 var video: Video
    @State private var player = AVPlayer(
    var body: some View {
        VideoPlayer(player: player)
    }
  }
struct VideoView_Previews: PreviewProvider {
    static var previews: some View {
        VideoView(video: previewVideo)
}
```
[video view play button.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20view%20play%20button.PNG)<br/>
Add constraints and video link for it to play:
```swift 
.edgesIgnoringSafeArea(.all)
            .onAppear{
                if let link = video.videoFiles.first?.link {
                    player = AVPlayer(url: URL(string: link)!)
                    player.play()
```
[video preview played.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20preview%20played.PNG)<br/>
## ***Generate API key for Pexels API***
Go to https://www.pexels.com/api/new and obtain a private API.<br/> 
In [ContentView.swift](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/PetsGalleryApp/Views/ContentView.swift), fetch videos in various categories with the imported API:
```swift 
NavigationView{
            VStack {
 false)
HStack {
    ForEach(Query.allCases, id: \.self){
        searchQuery in
        QueryTag(query: searchQuery, isSelected:
} }
ScrollView {
    ForEach(videoManager.videos, id: \.id) {
} }
video in
NavigationLink {
    VideoView(video: video)
} label: {
    VideoCard(video: video)
}
    .frame(maxWidth: .infinity)
}
.background(Color("AccentColor"))
```
[videos in categories fetched.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/videos%20in%20categories%20fetched.PNG)<br/>
Use
```swift 
LazyVGrid(columns: columns, spacing: 20)
```
method to make videos align better:<br/>
[videos aligned better.PNG](https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/videos%20aligned%20better.PNG)<br/>
Fetch all categories in dispatch queue:
```swift 
 DispatchQueue.main.async {
          // Reset the videos (for when we're calling the API again)
                self.videos = []
           // Assigning the videos we fetched from the API
                self.videos = decodedData.videos
            }
```
# Testing Result
<p align = "center">
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/all%20categories%20showed.PNG" width = "380" height = "848.81818">&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20card%20initial%20frame.PNG" width = "380" height = "848.81818">&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20play%20button.PNG" width = "380" height = "848.81818">&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20cover%20image%20displayed.PNG" width = "380" height = "848.81818">&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20view%20play%20button.PNG" width = "380" height = "848.81818">&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/video%20preview%20played.PNG" width = "380" height = "848.81818">&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/videos%20in%20categories%20fetched.PNG" width = "380" height = "848.81818">&nbsp; 
 <img src = "https://github.com/KrystalZhang612/PetsGalleryApp/blob/main/testing-result-PetsGalleryApp/videos%20aligned%20better.PNG" width = "380" height = "848.81818">&nbsp;  
</p>


# Tags and Topics





