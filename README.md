# diff
对原项目进行了一点修改，只输出两个文本的差异部分。方便只关心差异部分的应用使用，比如网站监控。  
Quick'n'easy string diffing functions for Golang based on [github.com/sergi/go-diff](https://github.com/sergi/go-diff). Mainly for diffing strings in tests.  

See [the docs on GoDoc](https://godoc.org/github.com/andreyvit/diff).  

Get it:  

    go get -u github.com/sanmin33/diff  

Example:  
```
    import (
        "strings"
        "testing"
        "github.com/sanmin33/diff"
    )

    const expected = `
    ...
    `

    func TestFoo(t *testing.T) {
        actual := Foo(...)
        if a, e := strings.TrimSpace(actual), strings.TrimSpace(expected); a != e {
            t.Errorf("Result not as expected:\n%v", diff.LineDiff(e, a))
        }
    }
```
