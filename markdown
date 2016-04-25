#!/usr/bin/env ruby

require 'github/markdown'

filename = File.basename(ARGV[0], ".*") + ".html"
puts ("Writing " + ARGV[0] + " to " + filename)
output = File.open(filename, "w")
output << (GitHub::Markdown.render_gfm File.read(ARGV[0]))
output.close
