# 创建数据库模型
Django是通过Model操作数据库，不管你数据库的类型是MySql或者Sqlite，Django它自动帮你生成相应数据库类型的SQL语句，所以不需要关注SQL语句和类型，对数据的操作Django帮我们自动完成。只要回写Model就可以了！

django根据代码中定义的类来自动生成数据库表。我们写的类表示数据库的表，如果根据这个类创建的对象是数据库表里的一行数据，对象.id 对象.value是每一行里的数据。

基本的原则如下：
1. 每个模型在Django中的存在形式为一个Python类
2. 每个模型都是django.db.models.Model的子类
3. 模型里的每个类代表数据库中的一个表
4. 模型的每个字段（属性）代表数据表的某一列
5. Django将自动为你生成数据库访问API


从之前的文章我们可以看到，如果我们想要将数据库的数据展现到网页上，需要由视图、模型与模板共同实现，步骤如下：

1. 在models.py里定义数据模型，以类的方式定义数据表的字段。在数据库创建数据表时，数据表由模型定义的类生成。
2. 在myblog的urls中注册url，确定返回的vies中定义的函数
3. 在视图views.py导入模型所定义的类，我们把这个类称之为数据表对象，然后在视图函数里使用Django的数据库操作方法，实现数据库操作，从而获取到数据表里的数据。
4. 视图函数获取到数据之后，将数据以字典、列表或对象（上下文context）的方式传递给HTML模板，并由模板引擎接收和解析，最后生成相应的HTML网页，在浏览器里展现出来。
