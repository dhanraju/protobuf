# protobuf
To tryout protobufs examples


Ref: https://developers.google.com/protocol-buffers/docs/overview?csw=1

# How do they work?
<ul>
<li>Specify the information we're serializing to be structured by defining protocl buffer message types in <span style="color: #6d9eeb">.proto</span> files.</li>
<li>Each proto buf message is a small logical record of information, containing a series of <em><strong style="color: red;">name-value pairs</strong></em>.</li>
</ul>

<pre><code>
message Person {
    required string name = 1;
    required int32 id = 2;
    optional string email = 3;

    enum PhoneType {
        MOBILE = 0;
        HOME = 1;
        WORK = 2;
    }

    message PhoneNumber {
        required string number = 1;
        optional PhoneType type = 2 [default = HOME];
    }

    repeated PhoneNumber phone = 4;
}
</code></pre>

* <em>Each message type</em> has one or more uniquely numbered fields, and each field has a name and a value type
* <em>Value types can be numbers</em> (int or float), booleans, strings, raw bytes or even other protocol buffer message types, allowing us to structure our data hierarchically.