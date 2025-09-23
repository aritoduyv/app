# Async Storage

AsyncStorage for Android uses SQLite for storage backend. While it has [its own size limits](https://www.sqlite.org/limits.html), Android system also have two known limits: total storage size and per-entry size limit.

* Total storage size is capped at 6 MB by default. You can increase this size by [specifying a new size using feature flag.](https://react-native-async-storage.github.io/async-storage/docs/advanced/db_size)
* Per-entry is limited by a size of a WindowCursor, a buffer used to read data from SQLite. [Currently it's size is around 2 MB](https://cs.android.com/android/platform/superproject/+/master:frameworks/base/core/res/res/values/config.xml;l=2103). This means that the single item read at one time cannot be larger than 2 MB. There's no supported workaround from AsyncStorage. We suggest keeping your data lower than that, by chopping it down into many entries, instead of one massive entry. This is where [`multiGet`](https://react-native-async-storage.github.io/async-storage/docs/api#multiget) and [`multiSet`](https://react-native-async-storage.github.io/async-storage/docs/api#multiset) APIs can shine.

