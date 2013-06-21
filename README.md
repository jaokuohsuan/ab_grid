ab_grid
=======

ab_grid 是一個依據特定邏輯去切分版面的css 流動布局系統，雖然有 grid 在名字內
但是不含有固定隔線系統在內，僅依據內容切分比例
建議使用在簡單的排版，較不易顯雜亂

如何使用
+ab_grid(a a a,b b)

將會產生一個 .columns_aaabb ，且 在其下的 .column 比例 為 3：2



ab_grid is a way to create fluid layout css ,depending on a specific logic class naming
there is no fix grid system in ad_grid, only split layout depend on naming


how to use

add new grid by ab_grid mixin
example: 
+ab_grid(a a a,b b)
will make 2 column layout ,with ratio 3:2  under .grid_aaabb


