NetworkManager is a lightweight Swift library designed to simplify network requests and data fetching in iOS applications. It provides a straightforward interface for making HTTP requests and handling responses with ease.

📌 Features
Simplified API for making network requests
Supports fetching and decoding JSON data
Error handling for network and decoding issues

🚀 Usage
1️⃣ Fetching Data
Here's how you can use NetworkManager to fetch and decode JSON data:

struct Article: Decodable {
    let title: String
    let body: String
}

let networkManager = NetworkManager()

let urlString = "https://api.example.com/articles/1"

networkManager.fetchData(urlString: urlString) { (result: Result<Article, Error>) in
    switch result {
    case .success(let article):
        print("Title: \(article.title)")
        print("Body: \(article.body)")
    case .failure(let error):
        print("Error fetching data: \(error.localizedDescription)")
    }
}
2️⃣ Handling Errors
NetworkManager provides custom error handling for various scenarios:

CustomErrors.wrongResponse: Indicates an invalid response or data.
CustomErrors.statusCode: Indicates an unexpected HTTP status code.
You can handle these errors in the completion handler as shown above.

🔧 Configuration
Currently, NetworkManager uses default configurations. For advanced usage, you might consider extending its functionality to support custom headers, HTTP methods, and request parameters.
