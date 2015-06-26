---
layout: post
title:  "Filter RSpec Tests"
date:   2015-06-25
---

Tag RSpec tests by putting a # and word at the start of a description string.

'''ruby
describe "#filter_technique" do
  it "works" do
    expect(appears_in_filtered_test_suite).to be true
  end
end

describe "not filtered" do
  it "doesn't work" do
    expect(appears_in_filtered_test_suite).to be false
  end
end
'''

Run your test suite with the tag and it will only run the tagged tests.

  rspec --tag filter_technique

  Pretty handy when you want to focus on the tests for the code you're working on.
