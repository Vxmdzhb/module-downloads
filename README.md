# astrx/module-downloads

Signed release downloads page with its admin editor — the **Downloads** module of [AstrX](https://github.com/Vxmdzhb/astrx).

![A signed release manifest, verified on the page](docs/screenshot.png)

- Module key: `downloads` (switch it on in the site's `resources/config/Modules.config.php`)
- Pages: `admin_downloads`, `downloads`
- Requires: `astrx/cms`, `astrx/framework`, `astrx/library`
- Suggests `ext-sodium`: Signs and verifies the release manifest (the page refuses to run without it)

It ships its own templates, catalogs (en, it), default configuration and SQL in
`resources/`; the site overrides any of them from its own `resources/`.

AstrX isn't on Packagist and doesn't tag versions: you install from each
repository's `main`, and your `composer.lock` pins the exact commit. Tell
Composer where to find the package and the AstrX packages it depends on:

```json
{
    "minimum-stability": "dev",
    "prefer-stable": true,
    "repositories": [
        { "type": "vcs", "url": "https://github.com/Vxmdzhb/module-downloads" },
        { "type": "vcs", "url": "https://github.com/Vxmdzhb/cms" },
        { "type": "vcs", "url": "https://github.com/Vxmdzhb/framework" },
        { "type": "vcs", "url": "https://github.com/Vxmdzhb/library" }
    ]
}
```

Then:

```sh
composer require astrx/module-downloads:dev-main
```

After that, list `AstrX\Downloads\DownloadsModule::class` in the
site's `ApplicationModules::INSTALLED` and run the installer to create its
tables. See [modules](https://github.com/Vxmdzhb/astrx/blob/main/docs/MODULES.md).

Issues and pull requests are welcome here. [AstrX](https://github.com/Vxmdzhb/astrx)
is the site that puts all the packages together.

## License

Released under the [Do Whatever License](LICENSE), with a code of conduct
in the same spirit: [CODE_OF_CONDUCT](CODE_OF_CONDUCT).
