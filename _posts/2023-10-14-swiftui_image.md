---
layout: post
title: SwiftUI - Image
---

어제는 SwiftUI의 Image에 대해서 봅시다.
공식 페이지는 다음과 같습니다
[Image](https://developer.apple.com/documentation/swiftui/image)

iOS 기준의 최소버전은 13.0입니다

공식적으로 PNG, JPEG, HEIC 등을 지원한다고 합니다. SVG등등...

다음과 같은 예제로 출력이 가능하다고 합니다

```
Image("Landscape_4")
    .resizable()
    .aspectRatio(contentMode: .fit)
Text("Water wheel")
```

그리고 표준 modifires를 가지고 이미지의 fitting을 할 수 있게 해준다고 합니다

modifier는
```
resizable(capInsets:resizingMode:)
```

### 생성자
Creates a labeled image that you can use as content for controls.
```
init(String, bundle: Bundle?)
```
Creates a labeled image that you can use as content for controls, with a variable value.
```
init(String, variableValue: Double?, bundle: Bundle?)
```
Initialize an Image with an image resource.
```
init(ImageResource)
```

### modifier
Sets the mode by which SwiftUI resizes an image to fit its space.
```
func resizable(capInsets: EdgeInsets, resizingMode: Image.ResizingMode) -> Image
```

modifier는 점점 추가하겠습니다
  