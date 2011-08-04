#You can include the php file in adhoc-task

This allows us to keep the code a little cleaner, more importantly.
When writing the php code, we get syntax highlighting and we can run tests on it.

```php
    <target name="test">
        <test-include hello="Chris"/>
    </target>
```

```php
    <adhoc-task name="test-include"><![CDATA[ include( "./test-include.php"); ]]></adhoc-task>
```

```php
    <?php
    class test_include extends Task {
    
        function setHello($name)
        {
            $this->name = $name;
        }   
    
        function main()
        {
            echo "Hello " . $this->name;
        }
    }
```


##Links
http://www.phing.info/docs/guide/current/chapters/appendixes/AppendixB-CoreTasks.html#AdhocTaskdefTask