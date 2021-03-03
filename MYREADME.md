# MY README libIEC61850

clone官方的源碼後，在這個檔案中留下自已的學習記錄

## Examples

範例程式是最好的學習對象，可惜官方在這部份說明太少，程式裡也缺少註解。

### goose_publisher
需以root身份執行，每一種網路介面（有線、無線、loopback）都能發出goose訊息，
這裡是以程式的方式直接發布（）Goose訊息，與一般Server使用Goose的方式不月口。

```
sudo ./goose_publisher_example wlp2s0
```

可以用tshark錄下goose封包：
```
tshark -i wlp2s0 --autostop duration:30 -F pcap -w test.pcap
```
### goose_subscriber
需以root身份執行，並非每一種網路介面都能收到goose訊息，測試迄今，有線、loopback都沒有問題，唯獨Asus G14筆電內建的wifi介面
無法收到goose訊息。

由於goose_publisher的程式寫成只發出三次goose訊息，建議先執行goose_subscriber，再執行goose_publisher。

```
sudo ./goose_subscriber_example enxf4285319dc80
```

這個程式也可以搭配server_example_goose範例程式使用，但App Id必須修改成4096，因為在cid檔裡App Id是十六進位值。
### iec61850_9_2_LE_example
### iec61850_client_example1
### iec61850_client_example

這是我最常用的客戶端範例程式，因為它提供了瀏覽Server上的data objects的功能，可以列印出有哪些data set、DO、DI、Report等等。

### iec61850_client_example4
### iec61850_client_example5
### iec61850_client_example_array
### iec61850_client_example_async
### iec61850_client_example_control
### iec61850_client_example_files
### iec61850_client_example_log
### iec61850_client_example_no_thread
### iec61850_client_example_reporting
### iec61850_client_file_async
### iec61850_sv_client_example
### mms_utility
### server_example_61400_25
### server_example_basic_io
### server_example_complex_array
### server_example_config_file
### server_example_control
### server_example_dynamic
### server_example_files
### server_example_goose

這個範例程式定義了一個具有兩個Goose control block的Server，需以root身份執行，可以用tshark錄下goose封包，或搭
配goose_subscriber範例程式使用，列印出收到的goose訊息。
```
sudo ./server_example_goose wlp2s0
```

### server_example_logging
### server_example_password_auth
### server_example_setting_groups
### server_example_simple
### server_example_substitution
### server_example_threadless
### server_example_write_handler
### sv_publisher
### sv_subscriber
### tls_client_example
### tls_server_example
