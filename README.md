<div align="center">

## Access Modifiers in \.Net \- An Explanation


</div>

### Description

Access modifiers are keywords which control the visibility of class members and other code constructs. But if you are confused what and when to use one Go ahead and read on... and if you find it useful plz vote.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Pankaj Nagar](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/pankaj-nagar.md)
**Level**          |Beginner
**User Rating**    |4.2 (46 globes from 11 users)
**Compatibility**  |C\#, VB\.NET, ASP\.NET, C\+\+\.NET
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__10-33.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/pankaj-nagar-access-modifiers-in-net-an-explanation__10-90/archive/master.zip)





### Source Code

<html>
<head>
<meta name="GENERATOR" content="Microsoft FrontPage 5.0">
<meta name="ProgId" content="FrontPage.Editor.Document">
<meta http-equiv="Content-Type" content="text/html; charset=windows-1252">
<title>New Page 1</title>
</head>
<body>
<font SIZE="5"><b>
<p>.NET access modifiers</p>
</b></font><font FACE="Times New Roman">
<p>Access modifiers are keywords which control the visibility of class members
and other code constructs.</p>
<p>The access modifiers in .NET are </p>
<dir>
 <dir>
 <b>
 <p>1. public</p>
 <p>2. private </p>
 <p>3. protected</p>
 <p>4. internal</p>
 <p>5. protected internal</p>
 </dir>
</dir>
</b>
<p>These keywords control the visibility of class members (and other things),
defining the circumstances under which a member may be accessed-hence their
collective name as access modifiers. With the exception of the last, protected
internal, it's illegal to combine two access modifiers. Let's look at what each
of these mean in turn when used in a .NET class.<br>
</p>
<b>
<p>Public</b> means just that: public and visible to everyone and everything. A
public member can be accessed using an instance of a class, by a class's
internal code, and by any descendants of a class.</p>
<p>Lets say a class exists as </p>
<dir>
 <dir>
 <p>Class BaseFoo </p>
 <p>Public A</p>
 </dir>
</dir>
<p>Cases in which it can be accessed are as follows</p>
<dir>
 <dir>
 <p>1. By an instance like</p>
 <dir>
  <dir>
  <p>Foo = new BaseFoo</p>
  <p>Foo.A</p>
  </dir>
 </dir>
 <p>2. By a descendent class like</p>
 <dir>
  <dir>
  <p>Class ChildFoo</p>
  <p>Inherits BaseFoo</p>
  <p>MyBase.A</p>
  </dir>
 </dir>
 </dir>
</dir>
<b>
<p>Private</b> means hidden and usable only by the class itself. No code using a
class instance can access a private member and neither can a descendant class.
Information or functionality that will not be needed or has no meaning outside
of the context of a specific class should be made private.</p>
<dir>
 <dir>
 <p>1. Cannot be accessed by an instance</p>
 <p>2. Cannot be accessed by a descendent class</p>
 </dir>
</dir>
<b>
<p>Protected</b> members are similar to private ones in that they are accessible
only by the containing class. However, protected members also may be used by a
descendant class. So members that are likely to be needed by a descendant class
should be marked protected.</p>
<dir>
 <dir>
 <p>1. Cannot be accessed by an Instance of the class</p>
 <p>2. By a descendent class like</p>
 <dir>
  <dir>
  <p>Class ChildFoo</p>
  <p>Inherits BaseFoo</p>
  <p>MyBase.A</p>
  <p> </p>
  </dir>
 </dir>
 </dir>
</dir>
<b>
<p>Internal</b> are public to the entire application but private to any outside
applications (assembly). Internal is useful when you want to allow a class to be used by
other applications but reserve special functionality for the application that
contains the class.</p>
<p>Say a class exists in Application 1 as </p>
<dir>
 <dir>
 <p>Class BaseFoo </p>
 <p>Public A</p>
 </dir>
</dir>
<p>Cases in which it can be accessed from Application 1 are as follows</p>
<dir>
 <dir>
 <p>1. By an instance like</p>
 <dir>
  <dir>
  <p>Foo = new BaseFoo</p>
  <p>Foo.A</p>
  </dir>
 </dir>
 <p>2. By a descendent class like</p>
 <dir>
  <dir>
  <p>Class ChildFoo</p>
  <p>Inherits BaseFoo</p>
  <p>MyBase.A</p>
  </dir>
 </dir>
 </dir>
</dir>
<p>But from an Application 2 if you have reference to BaseFoo of Application1
even then A cannot be accessed. </p>
<dir>
 <dir>
 <p>1. Cannot be accessed by an instance</p>
 <p>2. Cannot be accessed by a descendent class</p>
 </dir>
</dir>
<p>Finally, we have the only compound access modifier allowed in .NET, </p>
<b>
<p>protected internal</b>: Members marked as protected internal may be accessed
only by a descendant class that's contained in the same application as its base
class. You use protected internal in situations where you want to deny access to
parts of a class' functionality to any descendant classes found in other
applications. Not limited to controlling class access</p>
<p>Say a class exists in Application 1 as </p>
<dir>
 <dir>
 <p>Class BaseFoo </p>
 <p>Public A</p>
 </dir>
</dir>
<p>Cases in which it can be accessed from Application 1 are as follows</p>
<dir>
 <dir>
 <p>1. Cannot be accessed by an instance</p>
 <p>2. Can be accessed by a descendent class like</p>
 <dir>
  <dir>
  <p>Class ChildFoo</p>
  <p>Inherits BaseFoo</p>
  <p>MyBase.A</p>
  </dir>
 </dir>
 </dir>
</dir>
<p>But from an Application 2 if you have reference to BaseFoo of Application1
even then A cannot be accessed. </p>
<dir>
 <dir>
 <p>1. Cannot be accessed by an instance</p>
 <p>2. Cannot be accessed by a descendent class</p>
 </dir>
</dir>
<p>Access modifiers aren't limited to use on class members but can be applied to
a few other code constructs. The rules defining when modifiers may be legally
assigned to a construct are dependant on the construct's container:</p>
<dir>
 <i><b>
 <p>Interface</b></i> and <i><b>enumeration</b></i> members are always public
 and no access modifiers are needed (or allowed). </p>
 <p>Classes in <i><b>namespaces</b></i> are internal by default and may be
 either internal or public, while <i>namespaces</i> themselves are always
 public. </p>
 <p>Members of a <b><i>struct</i> </b>are private by default and may be given
 public, internal, or private access modifiers.</p>
</dir>
<p><br>
</p>
</font><font FACE="Arial" SIZE="2">
<p> </p>
</font>
</body>
</html>

