## $this 和 self 的使用时机
问题[链接](https://stackoverflow.com/questions/151969/when-to-use-self-over-this)

$this 代表当前对象
self  代表当前类

$this self 的正确用法示例

    class foo{
        private $non_static_mem = 1;
        private static $static_mem = 2;

        function __construct(){
            echoh $this->non_static_mem.' '.self::$static_mem;
        }
    }

$this 多态示例

    class X {
        function foo() {
            echo "X::foo()";
        }

        function bar() {
            $this->foo();
        }
    }
    class Y extends X {
        function foo() {
            echo "Y::foo";
        }
    }
    $x = new Y();
    $x->bar();
    //output Y::foo

self 压制多态的例子
    class X {
        function foo() {
            echo "X::foo()";
        }
        function bar() {
            self::foo();
        }
    }
    class Y extends X {
        function foo() {
            echo "Y::foo()";
        }
    }
    $x = new Y();
    $x->bar();
    //output X:foo()

