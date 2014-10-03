require 'fileutils'
require 'html/proofer'
require 'html/pipeline'
require 'find'

desc 'Clean up generated site'
task :clean do
  sh 'rm -rf _site'
end

task :test do
  FileUtils.rm_r "out" if File.exists?("out")
  Dir.mkdir("out")

  pipeline = HTML::Pipeline.new [
    HTML::Pipeline::MarkdownFilter,
    HTML::Pipeline::TableOfContentsFilter
  ], :gfm => true
end

task default: :test
