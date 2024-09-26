## 本项目实现的最终作用是基于SSM公司客户关系管理系统
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 员工管理
 - 客户管理
 - 用户管理
 - 管理员登录
### 第2个角色为员工角色，实现了如下功能：
 - 员工登录
 - 客户管理
 - 新增客户
 - 编辑客户
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssm_company_manage_sys

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [contact](#contact) |  |
| [customer](#customer) |  |
| [role_menu](#role_menu) | 权限关联表 |
| [sysmenu](#sysmenu) | 后台菜单表 |
| [sysrole](#sysrole) | 后台角色表 |
| [systemdef](#systemdef) |  |
| [sysuser](#sysuser) | 用户信息表 |
| [user_role](#user_role) | 后台角色与用户关联表 |
| [visitlog](#visitlog) |  |

**表名：** <a id="contact">contact</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | customerid |   int   | 10 |   0    |    N     |  Y   |       | 客户id  |
|  3   | name |   varchar   | 255 |   0    |    N     |  N   |       | 姓名  |
|  4   | position |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 职务  |
|  5   | tel |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 固话  |
|  6   | phone |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 手机  |
|  7   | qq |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | weixin |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  9   | email |   varchar   | 45 |   0    |    Y     |  N   |   NULL    | 邮箱  |

**表名：** <a id="customer">customer</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | name |   varchar   | 255 |   0    |    N     |  N   |       | 名称  |
|  3   | address |   varchar   | 255 |   0    |    N     |  N   |       | 地址  |
|  4   | zipcode |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 邮编  |
|  5   | fax |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 传真  |

**表名：** <a id="role_menu">role_menu</a>

**说明：** 权限关联表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | role_id |   int   | 10 |   0    |    N     |  N   |       | 角色ID  |
|  3   | menu_id |   int   | 10 |   0    |    N     |  N   |       |   |

**表名：** <a id="sysmenu">sysmenu</a>

**说明：** 后台菜单表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | id  |
|  2   | name |   varchar   | 255 |   0    |    N     |  N   |   ''    | 菜单名称  |
|  3   | parentid |   int   | 10 |   0    |    N     |  N   |   0    | 父级菜单ID0表示根节点  |
|  4   | sequence |   int   | 10 |   0    |    N     |  N   |   0    | 菜单顺序  |
|  5   | iconCls |   varchar   | 255 |   0    |    N     |  N   |   ''    | 菜单图标样式  |
|  6   | url |   varchar   | 255 |   0    |    N     |  N   |   ''    | 菜单链接地址总是以‘/’开头，相对于项目根路径  |
|  7   | enable |   int   | 10 |   0    |    N     |  N   |   1    | 是否可用1:正常，0：禁用  |

**表名：** <a id="sysrole">sysrole</a>

**说明：** 后台角色表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | name |   varchar   | 60 |   0    |    N     |  N   |   ''    | 角色名称  |

**表名：** <a id="systemdef">systemdef</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 部门编号  |
|  2   | name |   char   | 20 |   0    |    N     |  N   |       | 部门名称  |
|  3   | parentid |   int   | 10 |   0    |    N     |  N   |   0    | 所属二级部门【父类（上级部门）】  |
|  4   | iconCls |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 样式  |
|  5   | ptopid |   int   | 10 |   0    |    N     |  N   |       | 所属一级部门【顶级父类】  |
|  6   | pthird |   int   | 10 |   0    |    Y     |  N   |   NULL    | 所属三级部门【扩展备用】  |

**表名：** <a id="sysuser">sysuser</a>

**说明：** 用户信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | username |   varchar   | 255 |   0    |    N     |  N   |   ''    | 登录名（匿名）  |
|  3   | password |   varchar   | 255 |   0    |    N     |  N   |   ''    | 登录密码  |
|  4   | sysid |   int   | 10 |   0    |    N     |  N   |       | 所属部门  |
|  5   | email |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 邮件  |
|  6   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 真实姓名  |
|  7   | idcard |   varchar   | 255 |   0    |    N     |  Y   |       | 身份证  |
|  8   | gender |   varchar   | 2 |   0    |    N     |  N   |   '男'    | 性别1男2女  |
|  9   | qq |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | qq  |
|  10   | weixin |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  11   | regtime |   date   | 10 |   0    |    N     |  N   |       | 入职日期  |

**表名：** <a id="user_role">user_role</a>

**说明：** 后台角色与用户关联表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | UserId |   int   | 10 |   0    |    N     |  N   |       | 用户ID  |
|  3   | roleId |   int   | 10 |   0    |    N     |  N   |       | 角色ID  |

**表名：** <a id="visitlog">visitlog</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | customerid |   int   | 10 |   0    |    Y     |  N   |   NULL    | 客户id  |
|  3   | idcard |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 身份证信息  |
|  4   | vdate |   date   | 10 |   0    |    Y     |  N   |   NULL    | 拜访日期  |
|  5   | vtype |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 拜访方式  |
|  6   | vremark |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 拜访记录  |

