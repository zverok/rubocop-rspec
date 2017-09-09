# Change log

## Master (Unreleased)

* Add `RSpec/Capybara` namespace including the first cop for feature specs: `Capybara/FeatureMethods`. ([@rspeicher][])
* Fixed false positives in 'RSpec/ReturnFromStub' when string with variables interpolated is used. ([@Darhazer][])

## 1.16.0 (2017-09-06)

* Add `RSpec/FactoryGirl` namespace including the first cop for factories: `FactoryGirl/DynamicAttributeDefinedStatically`. ([@jonatas][])
* Add disabled by default `RSpec/AlignLeftLetBrace`. ([@backus][])
* Add disabled by default `RSpec/AlignRightLetBrace`. ([@backus][])
* Add `RSpec/LetBeforeExamples` cop. ([@Darhazer][])
* Add `RSpec/MultipleSubjects` cop. ([@backus][])
* Add `RSpec/ReturnFromStub` cop. ([@Darhazer][])
* Add `RSpec/VoidExpect` cop. ([@pocke][])
* Add `RSpec/InvalidPredicateMatcher` cop. ([@pocke][])
* Change HookArgument cop to detect when hook has a receiver. ([@pocke][])
* Add `RSpec/PredicateMatcher` cop. ([@pocke][])
* Add `RSpec/ExpectInHook` cop. ([@pocke][])
* `RSpec/MultipleExpectations` now detects usage of expect_any_instance_of. ([@Darhazer][])
* `RSpec/MultipleExpectations` now detects usage of is_expected. ([@bmorrall][])

## 1.15.1 (2017-04-30)

* Fix the handling of various edge cases in the `RSpec/ExampleWording` cop, including one that would cause autocorrect to crash. ([@dgollahon][])
* Fix `RSpec/IteratedExpectation` crashing when there is an assignment in the iteration. ([@Darhazer][])
* Fix false positive in `RSpec/SingleArgumentMessageChain` cop when the single argument is a hash. ([@Darhazer][])

## 1.15.0 (2017-03-24)

* Add `RSpec/DescribeSymbol` cop. ([@rspeicher][])
* Fix error when `RSpec/OverwritingSetup` and `RSpec/ScatteredLet` analyzed empty example groups. ([@backus][])

## 1.14.0 (2017-03-24)

* Add `RSpec/OverwritingSetup` cop. ([@Darhazer][])
* Add autocorrect support for `RSpec/LeadingSubject` cop. ([@Darhazer][])
* Add `RSpec/ScatteredLet` cop. ([@Darhazer][])
* Add `RSpec/IteratedExpectation` cop. ([@Darhazer][])
* Add `RSpec/EmptyLineAfterSubject` cop. ([@Darhazer][])
* Add `RSpec/EmptyLineAfterFinalLet` cop. ([@Darhazer][])

## 1.13.0 (2017-03-07)

* Add repeated 'it' detection to `RSpec/ExampleWording` cop. ([@dgollahon][])
* Add [observed_nesting/max_nesting] info to `RSpec/NestedGroups` messages. ([@dgollahon][])
* Add `RSpec/ItBehavesLike` cop. ([@dgollahon][])
* Add `RSpec/SharedContext` cop. ([@Darhazer][])
* `Rspec/MultipleExpectations`: Count aggregate_failures block as single expectation. ([@Darhazer][])
* Fix `ExpectActual` cop flagging `rspec-rails` routing specs. ([@backus][])
* Fix `FilePath` cop not registering offenses for files like `spec/blog/user.rb` when it should be `spec/blog/user_spec.rb`. ([@backus][])

## 1.12.0 (2017-02-21)

* Add `RSpec/InstanceSpy` cop. ([@Darhazer][])
* Add `RSpec/BeforeAfterAll` for avoiding leaky global test setup. ([@cfabianski][])

## 1.11.0 (2017-02-16)

* Add `AroundBlock` cop. ([@Darhazer][])
* Add `EnforcedStyle` configuration for `RSpec/DescribedClass` cop. ([@Darhazer][])
* Fix false positive for `RSpec/RepeatedExample` cop. ([@redross][])

## 1.10.0 (2017-01-15)

* Fix false negative for `RSpec/MessageSpies` cop. ([@onk][])
* Fix internal dependencies on RuboCop to be compatible with 0.47 release. ([@backus][])
* Add autocorrect support for `SingleArgumentMessageChain` cop. ([@bquorning][])
* Rename `NestedGroups`' configuration key from `MaxNesting` to `Max` in order to be consistent with other cop configuration. ([@backus][])
* Add `RepeatedExample` cop for detecting repeated examples within example groups. ([@backus][])
* Add `ScatteredSetup` cop for enforcing that only one `before`, `around`, and `after` hook are used per example group scope. ([@backus][])
* Add `ExpectOutput` cop for recommending `expect { ... }.to output(...).to_stdout`. ([@backus][])

## 1.9.1 (2017-01-02)

* Fix unintentional regression change in `NestedGroups` reported in #270. ([@backus][])
* Change `MaxNesting` for `NestedGroups` from 2 to 3. ([@backus][])

## 1.9.0 (2016-12-29)

* Add `MessageSpies` cop for enforcing consistent style of either `expect(...).to have_received` or `expect(...).to receive`, intended as a replacement for the `MessageExpectation` cop. ([@bquorning][])
* Fix `DescribeClass` to not flag `describe` at the top of a block of shared examples. ([@clupprich][])
* Add `SingleArgumentMessageChain` cop for recommending use of `receive` instead of `receive_message_chain` where possible. ([@bquorning][])
* Add `RepeatedDescription` cop for detecting repeated example descriptions within example groups. ([@backus][])

## 1.8.0 (2016-10-27)

* Optionally ignore method names in the `describe` argument when running the `FilePath` cop. ([@bquorning][])
* Fix regression in how `FilePath` converts alphanumeric class names into paths. ([@bquorning][])
* Add `ImplicitExpect` cop for enforcing `should` vs. `is_expected.to`. ([@backus][])
* Disable `MessageExpectation` cop in the default configuration. ([@bquorning][])

## 1.7.0 (2016-08-24)

* Add support for checking all example groups with `ExampleLength`. ([@backus][])
* Add support for checking shared example groups for `DescribedClass`. ([@backus][])
* Add support for checking `its` from [rspec-its](https://github.com/rspec/rspec-its). ([@backus][])
* Add `EmptyExampleGroup` cop for detecting `describe`s and `context`s without any tests inside. ([@backus][])
* Add `CustomIncludeMethods` configuration option for `EmptyExampleGroup`. ([@backus][])
* Add `NestedGroups` cop for detecting excessive example group nesting. ([@backus][])
* Add `MaxNesting` configuration option for `NestedGroups` cop. ([@backus][])
* Add `ExpectActual` cop for detecting literal values within `expect(...)`. ([@backus][])
* Add `MultipleExpectations` cop for detecting multiple `expect(...)` calls within one example. ([@backus][])
* Add `Max` configuration option for `MultipleExpectations`. ([@backus][])
* Add `SubjectStub` cop for testing stubbed test subjects. ([@backus][])
* Add `LetSetup` cop for detecting cases where `let!` is used for test setup. ([@backus][])
* Change all cops to only inspect files with names following rspec convention (`*/spec/*` and/or `_spec.rb`). ([@backus][])
* Add `AllCops/RSpec` configuration option for specifying custom spec file patterns. ([@backus][])
* Add `AssignmentOnly` configuration option for `RSpec/InstanceVariable` cop. ([@backus][])
* Add `BeEql` cop which looks for expectations that can use `be(...)` instead of `eql(...)`. ([@backus][])
* Add autocorrect support for `BeEql` cop. ([@backus][])
* Add `MessageExpectation` cop for enforcing consistent style of either `expect(...).to receive` or `allow(...).to receive`. ([@backus][])
* Add `MessageChain` cop. ([@bquorning][])

## 1.6.0 (2016-08-03)

* Add `SkipBlocks` option for `DescribedClass` cop. ([@backus][])

## 1.5.3 (2016-08-02)

* Add `RSpec/NamedSubject` cop. ([@backus][])

## 1.5.2 (2016-08-01)

* Drop support for ruby `2.0.0` and `2.1.0`. ([@backus][])
* Internal refactorings and improved test coverage. ([@backus][])

## 1.5.1 (2016-07-20)

* Fix `unrecognized parameter RSpec/VerifiedDoubles:IgnoreSymbolicNames` warning. ([@jeffreyc][])
* Update to rubocop 0.41.2. ([@backus][])

## 1.5.0 (2016-05-17)

* Expand `VerifiedDoubles` cop to check for `spy` as well as `double`. ([@andyw8][])
* Enable `VerifiedDoubles` cop by default. ([@andyw8][])
* Add `IgnoreSymbolicNames` option for `VerifiedDoubles` cop. ([@andyw8][])
* Add `RSpec::ExampleLength` cop. ([@andyw8][])
* Handle alphanumeric class names in `FilePath` cop. ([@andyw8][])
* Skip `DescribeClass` cop for view specs. ([@andyw8][])
* Skip `FilePath` cop for Rails routing specs. ([@andyw8][])
* Add cop to check for focused specs. ([@renanborgescampos][], [@jaredmoody][])
* Clean-up `RSpec::NotToNot` to use same configuration semantics as other Rubocop cops, add autocorrect support for `RSpec::NotToNot`. ([@baberthal][])
* Update to rubocop 0.40.0. ([@nijikon][])

## 1.4.1 (2016-04-03)

* Ignore routing specs for DescribeClass cop. ([@nijikon][])
* Move rubocop dependency to runtime. ([@nijikon][])
* Update to rubocop 0.39.0. ([@nijikon][])

## 1.4.0 (2016-02-15)

* Update to rubocop 0.37.2. ([@nijikon][])
* Update ruby versions we test against. ([@nijikon][])
* Add `RSpec::NotToNot` cop. ([@miguelfteixeira][])
* Add `Rspec/AnyInstance` cop. ([@mlarraz][])

## 1.3.1

* Fix auto correction issue - syntax had changed in RuboCop v0.31. ([@bquorning][])
* Add RuboCop clone to vendor folder - see #39 for details. ([@bquorning][])

## 1.3.0

* Ignore non string arguments for FilePathCop - thanks to @deivid-rodriguez. ([@geniou][])
* Skip DescribeMethod cop for tagged specs. ([@deivid-rodriguez][])
* Skip DescribeClass cop for feature/request specs. ([@deivid-rodriguez][])

## 1.2.2

* Make `RSpec::ExampleWording` case insensitive. ([@geniou][])

## 1.2.1

* Add `RSpec::VerifiedDoubles` cop. ([@andyw8][])

## 1.2.0

* Drop support of ruby `1.9.2`. ([@geniou][])
* Update to RuboCop `~> 0.24`. ([@geniou][])
* Add `autocorrect` to `RSpec::ExampleWording`. This experimental - use with care and check the changes. ([@geniou][])
* Fix config loader debug output. ([@geniou][])
* Rename `FileName` cop to `FilePath` as a workaround - see [#19](https://github.com/nevir/rubocop-rspec/issues/19). ([@geniou][])

## 1.1.0

* Add `autocorrect` to `RSpec::DescribedClass` cop. ([@geniou][])

## 1.0.1

* Add `config` folder to gemspec. ([@pstengel][])

## 1.0.rc3

* Update to RuboCop `>= 0.23`. ([@geniou][])
* Add configuration option for `CustomTransformation` to `FileName` cop. ([@geniou][])

## 1.0.rc2

* Gem is no longer 20MB (sorry!). ([@nevir][])
* `RspecFileName` cop allows for method specs to organized into directories by class and type. ([@nevir][])

## 1.0.rc1

* Update code to work with rubocop `>= 0.19`. ([@geniou][])
* Split `UnitSpecNaming` cop into `RSpecDescribeClass`, `RSpecDescribeMethod` and `RSpecFileName` and enabled them all by default. ([@geniou][])
* Add `RSpecExampleWording` cop to prevent to use of should at the beginning of the spec description. ([@geniou][])
* Fix `RSpecFileName` cop for non-class specs. ([@geniou][])
* Adapt `RSpecFileName` cop to commen naming convention and skip spec with multiple top level describes. ([@geniou][])
* Add `RSpecMultipleDescribes` cop to check for multiple top level describes. ([@geniou][])
* Add `RSpecDescribedClass` to promote the use of `described_class`. ([@geniou][])
* Add `RSpecInstanceVariable` cop to check for the usage of instance variables. ([@geniou][])

<!-- Contributors -->

[@andyw8]: https://github.com/andyw8
[@backus]: https://github.com/backus
[@bquorning]: https://github.com/bquorning
[@deivid-rodriguez]: https://github.com/deivid-rodriguez
[@geniou]: https://github.com/geniou
[@jawshooah]: https://github.com/jawshooah
[@nevir]: https://github.com/nevir
[@nijikon]: https://github.com/nijikon
[@pstengel]: https://github.com/pstengel
[@miguelfteixeira]: https://github.com/miguelfteixeira
[@mlarraz]: https://github.com/mlarraz
[@renanborgescampos]: https://github.com/renanborgescampos
[@jaredmoody]: https://github.com/jaredmoody
[@baberthal]: https://github.com/baberthal
[@jeffreyc]: https://github.com/jeffreyc
[@clupprich]: https://github.com/clupprich
[@onk]: https://github.com/onk
[@Darhazer]: https://github.com/Darhazer
[@redross]: https://github.com/redross
[@cfabianski]: https://github.com/cfabianski
[@dgollahon]: https://github.com/dgollahon
[@rspeicher]: https://github.com/rspeicher
[@jonatas]: https://github.com/jonatas
[@pocke]: https://github.com/pocke
[@bmorrall]: https:/github.com/bmorrall
