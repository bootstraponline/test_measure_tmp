#### To Do

- Save execution time for each test. (this may already be in the minitest logs)
- Save overall execution time.
- Fix test numbering. 01, 02, etc.
- Better ways to format test names

```ruby
 lines.split("\n").each { |l| puts File.basename(l.split(',').first) }; nil
```

- Aggregate common errors

```ruby
Dir.glob('/tmp/flaky/fail/**/*') { |f| puts f if File.file?(f) && File.readlines(f).to_s.include?('Object.afterWrite') }

Dir.glob('/tmp/flaky/fail/**/*') { |f| puts f if File.file?(f) && File.readlines(f).to_s.include?('target application appears to have died') }
```
