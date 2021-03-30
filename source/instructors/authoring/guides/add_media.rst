.. meta::
   :description: Adding Media

## Adding media
You can insert Audio, Images and Videos into a page.

### Audio
You can insert and play audio files within your project.

On the page you wish to play Audio, go to the **Settings** area where you can define the source audio file along with any actions the should be triggered at specific times during playback.

![authtoken](/img/guides/media.png)

- **Source Name** - select the source file either from `.guides/media` folder if already uploaded to the project or upload directly from your PC where it will then be stored in the `.guides/media` folder.
- **Add Action** - specifies actions that are triggered at specific times during playback. The following options are available.

  Open file
  Close file
  Open Terminal
  Close Terminal
  Run command
  Highlight
  Close all tabs
  Pause


### Images
Inserting an image is similar. Here are some examples. PNG and JPG image types are supported. Note that the 2nd and 3rd examples point to images within your project.

Generally speaking, you should put your images in the `.guides/img` folder in order to keep the rest of your workspace free of extraneous content for the benefit of the student.

```markdown
![optional alt tag](http://any-url-you-like.png)
![](image-in-project-root.jpg)
![](.guides/img/best-place-for-images.png)
```


You can also drag/drop images from your project file tree into your content. They will be automatically tagged with the correct path.

For Markdown pages:

```markdown
![.guides/img/displayimage](.guides/img/displayimage.png)
```

For HTML pages:

```html
![.guides/img/displayimage](.guides/img/displayimage.png)
```


### Videos

Including embedded videos are also possible using the standard `<iframe>` html tag.


#### YouTube

If you wish to embed a YouTube video, go to the Share option and select **Embed** to obtain the code snippet.

![authtoken](/img/guides/guides_youtube.png)

```
<iframe width="560" height="315" src="//www.youtube.com/embed/1JNhoVbmNAo" frameborder="0" allowfullscreen></iframe>
```

#### Vimeo

  If you wish to embed a Vimeo video, go to the Share option and select **Embed** to obtain the code snippet.

![authtoken](/img/guides/guides_vimeo.png)

```
<iframe src="//player.vimeo.com/video/110479088" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="http://vimeo.com/110479088">Codio - Innovation in Computer Programming Education</a> from <a href="http://vimeo.com/user20752628">Codio</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
```

### Hyperlinks
Creating a hyperlink on a piece of text is easy.

```markdown
Go to [Google](google.com) to look stuff up.
```



### iframes

You can embed content in an iframe using the `<iframe>` html tag.

To embed from Google Docs, go to **File>Publish** to Web and select **Embed** to get the code snippet

![authtoken](/img/guides/guides_publish.png)


### Example Projects
https://codio.com/codio-units/java-example is a project that you can [copy](/project/ide/features/#copying-a-project) into your own Codio account and shows you how to create code tests and setup automatic marking. We would also recommend that you check out our [Guides Cheat Sheet](https://codio.com/home/starter-packs/cb114a27-d88e-4b74-a2a0-518ccb30dc44/) and **Use Pack** to create into your Codio account to review.