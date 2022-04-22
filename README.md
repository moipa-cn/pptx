# pptx

## A Golang library for replacing text or image in pptx file

For the method of processing pptx files, refer to [https://github.com/nguyenthenguyen/docx](https://github.com/nguyenthenguyen/docx)

### About
> The library replacing text or image in slides

> delete password only document edit password

> the theme rename

<mark>test file password is 123456


### Examples

```
package main

import (
	"fmt"
	"github.com/moipa-cn/pptx"
)

func main() {
	p,_:=pptx.ReadPowerPoint("./test.pptx")
	img := "./test.jpg"
	p.DeletePassWord()
	p.ReplaceSlideString("A Golang library", "welcome", -1)
	p.ReplaceNotesSlideString("TEST NotesSlides", "New NotesSlide", -1)
	p.ReplaceThemeName("ThemeName", "NewThemeName", -1)
	err := p.DeleteSlide(-1)
	if err != nil {
		fmt.Println(err)
	}
	p.ReplaceImage(img, 1)
	p.WriteToFile("./test_1.pptx")
}
```


### Todo
1. ppt to pptx
2. pptx to img
3. pptx to pdf
4. add slide
5. replace theme

