# golang-gtk3
How to translate golang with gotk3 on ubuntu 16.04
1. download gotk3 (v 0.6.0)  
$go get -f github.com/gotk3/gotk3/... 
2. edit local glib.go  
    //FORMAT_SIZE_BITS      FormatSizeFlags = C.G_FORMAT_SIZE_BITS  
    FORMAT_SIZE_BITS        FormatSizeFlags = 1 << 2
3. edit local quark.go  
    /*  
    #include <stdlib.h>  
    #include <glib.h>  
    */  
    import "C"  
4. compile & install gotk3  
$go install -tags "pango_1_42 gtk_3_18" github.com/gotk3/gotk3/...
6. create app
7. build app  
$go mod init app_name  
$go mod tidy  
$go build -tags "pango_1_42 gtk_3_18" .  
