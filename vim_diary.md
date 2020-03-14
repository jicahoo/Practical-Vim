1. vim grep
* `:vimgrep /hello/ cp/components/**/*.*`

2. vim find
* `:!find cp/obj/KITTYHAWK_DEBUG/cp/ -name EMC_UIS_APP_ProvisioningService.hpp`

3. run many commands on the same line
* `:echo "hello" | echo "good bye"`

4. Fastly open buffer. substring_of_file_path that can identiy that file. For example, cp/components/UI/CLI/plugins/commands/app/src/vvol/VvolSnapRequestRecImpl.cxx :b Snap
* `:b {substring_of_file_path}`

5. In C++, change the . operation to -> operation.
* Find '.', type 's' command to delete '.' and switch into insert mode, type '->', then find next '.', type '.' command to repeat. Cool!
* key sequence: `f.s-><Esc>;s-><Esx>`
