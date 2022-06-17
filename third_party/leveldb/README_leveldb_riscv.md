库代码存放路径：./third_party/leveldb

修改添加依赖的编译脚本，路径：/developtools/bytrace_standard/ohos.build

   {
     "subsystem": "developtools",
     "parts": {
       "bytrace_standard": {
         "module_list": [
           "//developtools/bytrace_standard/interfaces/innerkits/native:bytrace_core",
           "//developtools/bytrace_standard/bin:bytrace_target",
           "//developtools/bytrace_standard/bin:bytrace.cfg",
           "//developtools/bytrace_standard/interfaces/kits/js/napi:bytrace",
           "//third_party/leveldb:leveldb"
           
         ],
         "inner_kits": [
           {
             "type": "so",
             "name": "//developtools/bytrace_standard/interfaces/innerkits/native:bytrace_core",
             "header": {
               "header_files": [
                 "bytrace.h"
               ],
               "header_base": "//developtools/bytrace_standard/interfaces/innerkits/native/include"
             }
           }
         ],
          "test_list": [
           "//developtools/bytrace_standard/bin/test:unittest"
         ]
       }
     }
   }
