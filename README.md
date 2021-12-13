strapi笔记

1.安装成功后，采用Create new collection type 创建表或数据集，就会形成接口

2.strapi配置mysql的方法，在config的database.js下配置如下参数

module.exports = ({ env }) => ({
  defaultConnection: 'default',
  connections: {
    default: {
      connector: 'bookshelf',
      settings: {
        client: 'mysql',
        host: env('DATABASE_HOST', ''),
        port: env.int('DATABASE_PORT', 3306),
        database: env('DATABASE_NAME', 'test'),
        username: env('DATABASE_USERNAME', 'root'),
        password: env('DATABASE_PASSWORD', 'root'),
        ssl: env.bool('DATABASE_SSL', false),
      },
      options: {}
    },
  },
});

