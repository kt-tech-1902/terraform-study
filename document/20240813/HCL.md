# HCL

拡張子は tf

## 構成について

ブロックと引数で構成されている

```
<block> <parameters> {
    keys1 = value1
    keys2 = value2
}

```

一例

```
// resource = block name
// local_file = resource name(_の前が対象のプロバイダ、_の後がリソースのタイプ)
// pet = リソースを識別する論理名
resource "local_file" "pet" {
    // 引数(keyは固有)
    filename = "/root/pets.txt"
    context = "we love pet"
}

```
