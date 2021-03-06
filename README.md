# Config Assets
Simple &amp; Lightweight solution creating and loading config assets for Unity projects

## Install
Use [UpmGitExtension](https://github.com/mob-sakai/UpmGitExtension) (Recommended/Easier)

**Or**

Find `Packages/manifest.json` in your project and edit it to look like this:
```json
{
  "dependencies": {
    "caneva20.config-assets": "https://github.com/caneva20/ConfigAssets.git#0.2.0-preview.3",
    ...
  },
}
```

## Usage
First create a class and extend from `Config<T>`

```C#
public class MyConfig : Config<MyConfig> {}
```

Then add as many fields as you need, note that it must be Serializable by Unity for it to save

```C#
public class MyConfig : Config<MyConfig> {
    [SerializeField] private string _myString;
    [SerializeField] private bool _myBool = true;
    
    //This also works
    public int myInt;
}
```

And lastly, just call `YOUR_CLASS_NAME.Instance.YOUR_FIELD`

``` C#
int valueFromConfig = MyConfig.Instance.myInt;
```
