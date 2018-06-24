# QLPreviewController
A QLPreviewController object, or Quick Look preview controller, provides a specialized view for previewing an item. To display a Quick Look preview controller you have two options: You can push it into view using a [UINavigationController][1] object, or can present it modally, full screen, using the [present(_:animated:completion:)][2] method of its parent class, UIViewController.

QLPreviewController 객체 또는 Quick Look preview controller는 항목 미리보기를 위한 특별한 view를 제공합니다. Quick Look preview controller를 표시하려면 두 가지 옵션이 있습니다. [UINavigationController][1] 객체를 사용하여 view에 push를 하거나 부모 클래스 인 UIViewController의 [present(_:animated:completion:)][2] 메서드를 사용하여 모달로 전체 화면으로 표시 할 수 있습니다.

## Overview
A displayed preview includes a title taken from the last path component of the item URL. You can override this by implementing a [previewItemTitle][3] accessor for the preview item.

A Quick Look preview controller can display previews for the following items:
- iWork documents
- Microsoft Office documents (Office ‘97 and newer)
- Rich Text Format (RTF) documents
- PDF files
- Images
- Text files whose uniform type identifier (UTI) conforms to the public.text type (see [Uniform Type Identifiers Reference][4])
- Comma-separated value (csv) files
- 3D models in USDZ format (with both standalone and AR views for viewing the model)

To use a Quick Look preview controller, you must provide a data source object. The data source provides preview items to the controller and tells it how many items to include in a preview navigation list. If there is more than one item in the list, a modally-presented (that is, full-screen) controller displays navigation arrows to let the user switch among the items. For a Quick Look preview controller pushed using a navigation controller, you can provide buttons in the navigation bar for moving through the navigation list.

For details on providing items to a preview controller, refer to [QLPreviewControllerDataSource][5] and QLPreviewItem Protocol Reference.

표시된 미리보기에는 item URL의 마지막 경로 구성 요소에서 가져온 제목이 포함됩니다. 미리보기 항목에 대해 [previewItemTitle][3] 접근자를 구현하여 이 설정을 재정의 할 수 있습니다.

Quick Look preview controller는 다음 항목에 대한 미리보기를 표시 할 수 있습니다.
- iWork 문서
- Microsoft Office 문서 (Office '97 이상)
- 서식있는 텍스트 (RTF) 문서
- PDF 파일
- 이미지
- uniform type identifier (UTI)가 public.text 유형을 준수하는 텍스트 파일 ([Uniform Type Identifiers 참조][4])
- 쉼표로 구분 된 값 (csv) 파일
- USDZ 형식의 3D 모델 (모델을 보기위한 독립형 뷰와 AR 뷰 모두 있음)

Quick Look preview controller를 사용하려면 데이터 소스 개체를 제공해야 합니다. 데이터 소스는 미리보기 항목을 컨트롤러에 제공하고 미리보기 탐색 목록에 포함 할 항목 수를 알려줍니다. 목록에 둘 이상의 항목이있는 경우 모달 표시 (즉, 전체 화면) 컨트롤러는 사용자가 항목 사이를 전환 할 수 있도록 탐색 화살표를 표시합니다. 내비게이션 컨트롤러를 사용하여 푸시 된 훑어보기 미리 컨트롤러의 경우 네비게이션 목록에서 이동하기 위해 탐색 막대에 단추를 제공 할 수 있습니다.

preview controller에 항목을 제공하는 방법에 대한 자세한 내용은 [QLPreviewControllerDataSource][5] 및 QLPreviewItem 프로토콜 참조를 참조하십시오.

[Apple Documents][apple]


[1]: https://developer.apple.com/documentation/uikit/uinavigationcontroller
[2]: https://developer.apple.com/documentation/uikit/uiviewcontroller/1621380-present
[3]: https://developer.apple.com/documentation/quartz/qlpreviewitem/1419911-previewitemtitle
[4]: https://developer.apple.com/library/archive/documentation/Miscellaneous/Reference/UTIRef/Introduction/Introduction.html#//apple_ref/doc/uid/TP40009257
[5]: https://developer.apple.com/documentation/quicklook/qlpreviewcontrollerdatasource
[apple]: https://developer.apple.com/documentation/quicklook/qlpreviewcontroller
