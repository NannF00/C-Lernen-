# Entity Framework Core

https://developer.aliyun.com/article/686274

## 介绍

Entity Framework (EF) Core 是轻量化、可扩展和跨平台版的常用 Entity Framework 数据访问技术。

EF Core 可用作对象关系映射程序 (O/RM)，以便于 .NET 开发人员能够使用 .NET 对象来处理数据库，这样就不必经常编写大部分数据访问代码了。

EF Core 支持多个数据库引擎，请参阅数据库提供程序了解详细信息。

# 模型

对于 EF Core，使用模型执行数据访问。 模型由实体类(例如仓库类,产品类)和 表示数据库会话的派生上下文 构成，用于查询和保存数据。 有关详细信息，请参阅创建模型。

https://learn.microsoft.com/zh-cn/ef/core/modeling/?spm=a2c6h.12873639.article-detail.7.7d8a2164EqYX2x

可从现有数据库生成模型，手动编码模型使之与数据库相匹配，或使用 EF 迁移基于模型创建数据库（并在模型随时间推移发生更改后进行相应改进）。

    using Microsoft.EntityFrameworkCore;
    using System.Collections.Generic;

    namespace Intro
    {
        public class BloggingContext : DbContext
        {
            public DbSet<Blog> Blogs { get; set; }
            public DbSet<Post> Posts { get; set; }

            protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
            {
                optionsBuilder.UseSqlServer(@"Server=(localdb)\mssqllocaldb;Database=MyDatabase;Trusted_Connection=True;");
            }
        }

        public class Blog
        {
            public int BlogId { get; set; }
            public string Url { get; set; }
            public int Rating { get; set; }
            public List<Post> Posts { get; set; }
        }

        public class Post
        {
            public int PostId { get; set; }
            public string Title { get; set; }
            public string Content { get; set; }

            public int BlogId { get; set; }
            public Blog Blog { get; set; }
        }
    }
    
# 查询

使用语言集成查询 (LINQ) 从数据库检索实体类的实例。 有关详细信息，请参阅查询数据。

    using (var db = new BloggingContext())
    {
        var blogs = db.Blogs
            .Where(b => b.Rating > 3)
            .OrderBy(b => b.Url)
            .ToList();
    }

# 保存数据

使用实体类的实例在数据库中创建、删除和修改数据。 有关详细信息，请参阅保存数据。

    using (var db = new BloggingContext())
    {
        var blog = new Blog { Url = "http://sample.com" };
        db.Blogs.Add(blog);
        db.SaveChanges();
    }

# 后续步骤

有关介绍性教程，请参阅 Entity Framework Core 入门。

官方文档：https://docs.microsoft.com/zh-cn/ef/core/
