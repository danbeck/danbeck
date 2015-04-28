---
layout: post
title:  "Green Mahjong 2.2 released!"
date:   2014-10-23 20:14:00
categories: Green Mahjong
---

This new release of Green Mahjong is very special and exciting: we worked very hard at porting Green Mahjong on many more platforms. 
Until now, Green Mahjong was available on "Ubuntu touch", "FirefoxOS", "Desktop systems" ("Firefox" & "Chrome")


In the coming days, it will be published in the following stores:

- Android: [Green Mahjong][LinkToGooglePlay]
- Iphone
- Jolla

Whooo! :-)


Here is the full changelog:

- added chinese translation
- support for browser back
- new toolbar button for switching themes
- removed a bug which made tiles not selectable under the toolbar.
- made the game working on android, iphone and jolla.

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

```scala
package controllers.accounts

import play.api.Logger
import play.api.mvc._
import play.api.data.validation.Constraints
import views.html.workspace

class Workspace(override implicit val env: RuntimeEnvironment[User]) extends PhysalisSecureSocial {

  val USER_SERVICE = env.userService.asInstanceOf[UpdatableUserService]
  val z = "hallo"
  def user(username: String) = PhysalisUserAwareAction.async { implicit request =>
    def showMyAccount(user: User) = Future(Ok(workspace.myaccount(user)))
    def showPublicAccount(username: String) = Future.successful {
      User.findByUsername(username) match {
        case Some(user) => Ok(workspace.publicaccount(user))
        case None       => Ok(workspace.notExistingUser(null))
      }
    }
```

```scala
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```


[LinkToGooglePlay]: https://play.google.com/store/apps/details?id=de.beck.greenmahjong
