1. vim grep
* `:vimgrep /hello/ cp/components/**/*.*`

2. vim find
* `:!find cp/obj/KITTYHAWK_DEBUG/cp/ -name EMC_UIS_APP_ProvisioningService.hpp`

3. run many commands on the same line
* `:echo "hello" | echo "good bye"`

4. Fastly open buffer. substring\_of\_file\_path that can identiy that file. For example, cp/components/UI/CLI/plugins/commands/app/src/vvol/VvolSnapRequestRecImpl.cxx :b Snap
* `:b {substring_of_file_path}`

5. In C++, change the . operation to -> operation.
* Find '.', type 's' command to delete '.' and switch into insert mode, type '->', then find next '.', type '.' command to repeat. Cool!
* key sequence: `f.s-><Esc>;s-><Esx>`

6. In vim, show the hex value of decimal string.
* Yank the number string.  168
* `:echo printf("%x",@")`
* key sequenc: `vey:echo printf("%x",@")`
* v: visual mode, e:move to word end, y: copy the num str.

7. In vim, format text segement as xml.
* Sampe: `<hello> <world> Haha! </world> </hello>`
* Answer: 1. yank the text segement; 2. Use `:e temp.xml` to create a tempfil; 3. paste the text segemnt; 4. visual select the text `:'<,'>!xmllint --format -`
* Tips: the sign `-` in xmlint means reading from stdin.

8. Operate(delete, copy)  the contents between quotes, `\``, `'`, `"`, `{}`, `()`, `<>`, `[]`.
* Delete: 1. put curso in any char between the quotes. Then di", di}, or di{, and so on.
* Copy: just replace the 'd' with 'y'.
* Tips: it can also work on multiple lines.
* Example:
    ```text
    while (true) {
       line 1
       line 2
    }
    ```

9. Add line continuation for C++ macro, namely, use VIM to add char in one column.
* In Notepad++, it's easy to implement it using Alt+Mouse. In VIM, it's not.
* For now, I wrote a VIM script to implement this requirement.

```text
for i in range(4, 10)
  call cursor(i, 1)
  execute "normal" (20-strlen(getline("."))) . "A "
  execute "normal" "A\\"
endfor
```
* How to run this script? Input the script into vim. Yank these script lines. And call it via `:@"`.
* After run, the script will input `\` from line 4 to line 10 at column 20.

