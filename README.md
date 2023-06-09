# AWSCurl

Provides an _https/mqtt API_ for AWS. is inspired by [awscurl](https://github.com/okigan/awscurl), 
but does not provide a _CLI_, only an _API_ for similar functions.

# Example

```rs
use awscurl::{AWSCurl, AWSProfile, Method};

fn main() {
    let profile = AWSProfile::from_env().expect("can't read aws credentials");
    let awscurl = AWSCurl::new(&profile);
    awscurl.http_request(&Method::GET, "https://blog.com/users")
        .expect("can't fetch users");
}
```
