# UINavigationBar

[Apple Documentation](https://developer.apple.com/documentation/uikit/uinavigationbar)

viewDidLoad가 호출되는 단계에서는 아직 navigationController가 stack에 올라가기 전이기 때문에 navigationController에 대한 설정이 필요하면 viewWillAppear의 호출이나 그 이후에 설정하도록 하자.

```Swift
//Todo Now - ToDoListViewController.swift 

override func viewDidLoad() {
   super.viewDidLoad()
   searchBar.delegate = self
   tableView.separatorStyle = .none
 }


override func viewWillAppear(_ animated: Bool) {
   super.viewWillAppear(animated)
   if let colorHex = selectedCategory?.color {

      title = selectedCategory!.name
      guard let navBar = navigationController?.navigationBar else {fatalError("navigation controller does not exist")}

      if let navBarColor = UIColor(hexString: colorHex) {
         navBar.barTintColor = navBarColor
         navBar.tintColor = ContrastColorOf(navBarColor, returnFlat: true)
         navBar.largeTitleTextAttributes =
   [NSAttributedStringKey.foregroundColor : ContrastColorOf(navBarColor, returnFlat: true)]
         searchBar.barTintColor = navBarColor
      }
   }
}
```
