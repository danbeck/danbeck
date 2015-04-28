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

Test
```scala
package controllers.accounts

import play.api.Logger
import play.api.mvc._
import play.api.data.validation.Constraints
import views.html.workspace

class Workspace(override implicit val env: RuntimeEnvironment[User]) extends PhysalisSecureSocial {

  val USER_SERVICE = env.userService.asInstanceOf[UpdatableUserService]

  def user(username: String) = PhysalisUserAwareAction.async { implicit request =>
    def showMyAccount(user: User) = Future(Ok(workspace.myaccount(user)))
    def showPublicAccount(username: String) = Future.successful {
      User.findByUsername(username) match {
        case Some(user) => Ok(workspace.publicaccount(user))
        case None       => Ok(workspace.notExistingUser(null))
      }
    }

    request.user match {
      case Some(u) if u.usernameOption.get == username => showMyAccount(u)
      case Some(u)                                     => showPublicAccount(username)
      case None                                        => showPublicAccount(username)
    }
  }

  case class ProjectData(username: String, email: String, wantsNewsletter: Option[Boolean])

  val projectForm = Form(
    tuple(
      "gitUrl" -> nonEmptyText(7, 200).verifying { text => text.matches(s"https?://.*.git") },
      "appName" -> nonEmptyText(2, 70)))

  def newProjectPage = SecuredAction { implicit request =>
    Ok(workspace.myaccount(request.user, Some(projectForm)))
  }

  def createNewProject = SecuredAction.async {
    implicit request =>
      projectForm.bindFromRequest.fold(
        formWithErrors => redirectAndFlashError(),
        validInputData => updateUserAndRedirect(validInputData._2, validInputData._1, request))
  }

  private def redirectAndFlashError() = {
    Future.successful(Redirect(routes.Workspace.newProjectPage())
      .flashing("error" -> """The URL must end with ".git". """))
  }
}
```

```scala
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```


[LinkToGooglePlay]: https://play.google.com/store/apps/details?id=de.beck.greenmahjong
