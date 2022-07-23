# ngx_http_dongting_module

## Installation

***Clone the code***
    
    git clone https://github.com/selboo/ngx_http_dongting_module.git

***Build nginx with ngx_http_dongting_module***

    ./configure --add-module=/path/to/ngx_http_dongting_module
    make && sudo make install

## Directives

***dongting_log_escape_non_ascii***
  
    dongting_log_escape_non_ascii off ...

  * default value is *on*.

***dongting_format***
  
    dongting_format name string ...

  * syntax is same as log_format of HttpLogModule.
  * default value is *combined*.

***dongting_log***

    dongting_log command [format [nonblocking] [if=condition]];
 
    dongting_log off;
    
  * default value is *off*.

## Example

      dongting_format main '$remote_addr - $remote_user [$time_local] "$request" '
                        '$status $body_bytes_sent "$http_referer" '
                        '"$http_user_agent" "$http_x_forwarded_for"';
      
      dongting_log  logs/dongting.access.log  main;


