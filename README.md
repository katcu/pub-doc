# pub-doc
资料、文档
[测试](测试.md)

graph TD
    A[开始] --> B{输入 BOM 编号和版本号(可选)};
    B --> C[点击查询按钮];
    C --> D{查询数据库};
    D -- 查询成功 --> E{返回 MRP 数据} --> F[结束];
    alt BOM 编号为空
        B --> G[提示"请输入 BOM 编号"] --> B;
    end
    alt BOM 编号不存在
        D --> H[提示"BOM 编号不存在"] --> B;
    end
    alt 查询结果为空
        D --> I[提示"未找到符合条件的数据"] --> F;
    end
