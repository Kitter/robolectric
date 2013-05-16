# Robolectric Release Checklist

Set these properly:
```bash
ROBO_SRC=~/Development/robolectric
ROBO_DOCS=~/Development/robolectric-docs
```

* Ensure every story for this release in the Tracker project is accepted.
* Update release notes at `$ROBO_DOCS/release-notes.md`.
* `cd $ROBO_SRC && mvn clean release:clean release:prepare` (by xian)
* `cd $ROBO_SRC && mvn release:perform` (by xian)
* Update javadocs

```bash
cd $ROBO_SRC
git st # make sure there are no changes...
rm -rf javadocs/*
mv $ROBO_SRC/target/apidocs/* javadocs/
git commit -am "Update javadocs."
git push
```