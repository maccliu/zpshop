# bc_cart_item 基本表

购物车商品。

## SQL定义

```sql

DROP TABLE IF EXISTS `bc_cart_item`;

CREATE TABLE `bc_cart_item` (
  `cart_item_id` int(11) NOT NULL AUTO_INCREMENT,
  
  `cart_id` int(11) NOT NULL COMMENT '购物车id',
  `stu_id` int(11) NOT NULL COMMENT '商品id',
  `qty` int(11) unsigned NOT NULL COMMENT '商品数量',
  `checked` tinyint(1) NOT NULL DEFAULT '1' COMMENT '选中',
  
  `created_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `updated_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  
  PRIMARY KEY (`cart_item_id`),
  UNIQUE KEY `stu` (`cart_id`,`stu_id`),
  KEY `cart_id` (`cart_id`),
  KEY `stu_id` (`stu_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='购物车商品';


```

> 备注：
> 1. `checked` : 用户在购物车中是否选中此商品。1-选中，0-不选，默认是选中。
