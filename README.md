# basic-exercises
对于js的一些基本想法
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .wrap{
            width: 300px;
            height: 400px;
            margin: 50px auto;
        }
        .go,.over{
            width: 300px;
            height: 40px;
            margin: 15px 0;
            font-size: 22px;
            text-align: center;
            line-height: 30px;
        }
        a{
            width: 80px;
            height: 80px;
            border-radius: 10px;
            margin: 8px 8px 8px 8px;
            background: #FFA600;
            display: inline-block;
        }
        .go{
            color: #FFFFFF;
            background: #EE9900;
        }
        .over{
            color: #EE9900;
            background: #FFFFFF;
        }
    </style>
    <script src="jquery-1.11.1.min.js"></script>
    <script>
        $(function () {
            var $wrap=$('.wrap');
            var $a=$wrap.find('a');
            var $go=$('.go');
            var $over=$('.over');
            var timer=null;
            var temp="";
            var arr1=0;
            var arr2=0;
            var arr3=0;
            $go.click(function () {
                clearInterval(timer);
                timer=setInterval(function () {
                    $a.css('background','#FFA600');
                    arr1=parseInt(Math.random()*9);
                    arr2=parseInt(Math.random()*9);
                    arr3=parseInt(Math.random()*9);
                    console.log(arr1+','+arr2+','+arr3);
                    $a.eq(arr1).css('background',three());
                    $a.eq(arr2).css('background',three());
                    $a.eq(arr3).css('background',three());
            },1000)
            });
            $over.click(function () {
               clearInterval(timer);
                $a.css('background','#FFA600');
            });
            function three() {
                var temp='';
                var a="0123456789abcdef";
                var len=6;
                var tt='#';
                for(i=0;i<len;i++){
                    var t=parseInt(Math.random()*a.length);
                    temp+=a.charAt(t);
                }
                tt+=temp;
                return tt;
//                console.log(tt);
            }
        })
    </script>
</head>
<body>
<div class="wrap" id="wrap">
    <a href=""></a>
    <a href=""></a>
    <a href=""></a>
    <a href=""></a>
    <a href=""></a>
    <a href=""></a>
    <a href=""></a>
    <a href=""></a>
    <a href=""></a>
    <input type="button" value="开始" class="go" id="go">
    <input type="button" value="结束" class="over" id="over">
</div>
</body>
</html>
