
ab grid
=======


ab grid 是一個依據特定邏輯命名方式去切分版面的 css 流動布局系統，  
雖然有 grid 在名字內，但是不含有固定隔線系統在內，僅依據內容切分比例  
建議使用在簡單的排版，較不易顯雜亂
  

### 範例   
  demo url: [http://cdpn.io/dqJKb](http://cdpn.io/dqJKb) 

### 如何使用：

ab grid 包裝成 sass 的 mixin，使用如下


sass:   


    +ab_grid(a a a,b b)  
 

將會產生一個 .columns_aaabb ，且 在其下的 .column 比例 為 3：2

output css:  


    .grid_aaabb > .column:first-child {
      width: 57%;
      margin-right: 5%; }
    .grid_aaabb > .column:last-child {
      width: 38%;
      margin-right: 0; }


html 內使用，如下  

    <div class="grid_aaabb">  
    	<div class="column"></div>  
    	<div class="column"></div>  
    </div>    
  
  
  

### 修改預設名稱：

修改預設名稱，範例如下



    $container_name: "yes_" 
    $child_name: "worker" 


當輸入

     +ab_grid(1,2,3)

則產生如下結構  

    .yes_123  
      .worker  
      .worker  
      .worker   

    //....哈哈（冷）

### 修改預設值

    //修改grid的 margine-bottom 預設為 2em
    $grid_bottom: 2em  

    //修改 column 間隔 ,預設5%。 如輸入非 百分比% 單位， 將使用 calc() 
    $column_gutter: 5% 

    //修改 column 內 padding，預設為沒有
    $column_padding: 2%

### 其他設定

*  加入分隔線

	     //開啟分隔線設定，預設為開啟  //為產生附屬的 .with_line css  
	     $with_line: true 

	     // 分隔線顏色
	     $line_color: #ddd 

	使用法  
	    
	    <div class="grid_aaabb with_line">  
	    	<div class="column"></div>  
	    	<div class="column"></div>  
	    </div>   
*  加入 media query   
        
        //預設關閉 media query 設定 
        $with_media_query: false  
        
        //修改作用尺寸 ，預設為 480px
        $break-point: 480px   

        //每個column 下方分隔距離 ，預設為 1em          
        $column_gutter_media_query: 1em 

        //添加 grid 容器 左右 padding 以免黏至邊框，預設 5% 
        $edge_gutter_media_query: 5% 

    (僅提供最簡易的 media query)

** 大量使用 calc() 及 :nth-child()  ，請自行斟酌 瀏覽器支援度 **




*******


ab_grid is a way to create fluid layout css ,depending on a specific logic class naming.  
there is no fixed grid system in ad_grid, only split layout depend on naming.


### demo  
  demo url: [http://cdpn.io/dqJKb](http://cdpn.io/dqJKb) 
    
### how to use：

ab grid use sass mixin to create css, as below

sass:   


    +ab_grid(a a a,b b)  
 

will make 2 column layout ,with ratio 3:2  under .grid_aaabb

output css:  


    .grid_aaabb > .column:first-child {
      width: 57%;
      margin-right: 5%; }
    .grid_aaabb > .column:last-child {
      width: 38%;
      margin-right: 0; }


use in html   

    <div class="grid_aaabb">  
    	<div class="column"></div>  
    	<div class="column"></div>  
    </div>    
  
  
  

### change grid and column naming：

revise default naming，example:



    $container_name: "yes_" 
    $child_name: "worker" 


sass:  

     +ab_grid(1,2,3)

create structure as: 

    .yes_123  
      .worker  
      .worker  
      .worker   

### revise some default settings

    //revise grid margine-bottom, default is 2em
    $grid_bottom: 2em  

    //revise column gutter ,default is 5%. if unit of gutter is't %, will use calc() in css. 
    $column_gutter: 5% 

    //revise padding of columns,default is none
    $column_padding: 2%

### other settings

*  add border between column

	     //open $with_line setting ,default is true  //will create extend class .with_line  
	     $with_line: true 

	     // line color ,default is #ddd
	     $line_color: #ddd 

	how to use 
	    
	    <div class="grid_aaabb with_line">  
	    	<div class="column"></div>  
	    	<div class="column"></div>  
	    </div>   
*  add media query   
        
        //media query setting,default is false 
        $with_media_query: false  
        
        //revise break point,default is 480px
        $break-point: 480px   

        // column bottom gutter,default is 1em          
        $column_gutter_media_query: 1em 

        //add grid padding-left and padding-right, avoid content stick to edge,default is 5% 
        $edge_gutter_media_query: 5% 

    (only the most basic media query setting)  
 ** use a lot of calc() and :nth-child() ，plz consider browser support for your project **