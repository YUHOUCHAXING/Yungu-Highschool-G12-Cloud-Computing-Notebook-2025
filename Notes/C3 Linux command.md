# Linux 命令基础笔记

## 命令基本语法

命令的基本格式：
```bash
命令名 [command] [options] [arguments]
```

- **命令名**：存在于PATH环境变量中的可执行命令
- **command**：从属命令,可以是0~多个command
- **options**：
  - 单字母选项使用单个`-`（例如：`-a`，`-l`）
  - 单词选项使用双`--`（例如：`--help`）
- **arguments**：命令的参数

## 常用命令

### ls (List)
列出目录内容
- `ls` - 列出当前目录的文件和文件夹
- `ls -a` - 显示所有文件（包括隐藏文件）
- `ls -l` - 显示详细信息
- `ls -al` - 组合使用，显示所有文件的详细信息

### 帮助命令
获取命令帮助：
- `-h` 或 `--help` - 显示命令的简要帮助
- `man [命令名]` - 显示命令的详细手册页
  - 例如：`man ls`

## 文件权限管理

### 权限体系
文件权限格式：`-rwxrwx---`
- 第一个字符`-`：表示文件类型
  - `-`：普通文件
  - `d`：目录
  - `l`：符号链接
  - `b`：块设备文件
  - `c`：字符设备文件
  - `s`：套接字文件
  - `p`：管道文件
- 后面三组`rwx`：权限设置
  - 第一组`rwx`：所有者权限
  - 第二组`rwx`：用户组权限
  - 第三组`---`：其他用户权限

其中：
- `r`：读权限
- `w`：写权限
- `x`：执行权限

### 权限管理命令
1. `chmod` - 修改文件权限
   - 示例：`chmod 755 file.txt`
   - 数字权限说明：
     - `r` = 4（读权限）
     - `w` = 2（写权限）
     - `x` = 1（执行权限）
     - 数字权限是三个数字的组合，分别代表所有者、用户组和其他用户的权限
     - 例如：`755` = `rwxr-xr-x`
       - 第一个`7` = 4+2+1 = `rwx`（所有者权限）
       - 第二个`5` = 4+0+1 = `r-x`（用户组权限）
       - 第三个`5` = 4+0+1 = `r-x`（其他用户权限）

2. `chown` - 修改文件所有者和用户组
   - 示例：`chown user:group file.txt`

## 注意事项
- 命令选项可以组合使用
- 大多数命令都支持`--help`选项来获取帮助信息
- 权限管理需要相应的权限级别