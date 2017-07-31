=begin

  Rakefile created by Jae Hee Lee @ 2017

  The main reason for using Rake to generate files is to:

  1. ease the post creation process
  2. to assign 'random' hex for each post to uniquely identify posts
  independent from their variables

  I am about to add further functionalities in the future.

=end

require "rubygems"
require "rake"
require 'securerandom'
require "time"
require "fileutils"

SOURCE = '.'
CONFIG = {
  'version' => "1.0.0",
  'layouts' => File.join(SOURCE, "_layouts"),
  'posts' => File.join(SOURCE, "_posts"),
  'categories' => File.join(SOURCE, "category"),
  'post_ext' => "md",
}

# Usage: rake category title="" [href=""]  [id=""] [subcat_of="id of super category"]
# remove []! this is only to say that these fields are optional.
# By default, the href and id would be made by making the title lowercased.
desc "Create a new category in #{CONFIG['categories']}"
task :category do
  abort("rake aborted: '#{CONFIG['categories']}' directory not found.") unless FileTest.directory?(CONFIG['categories'])

  title = ENV['title'] || "rand-cat"
  href = ENV['href'] || title.downcase.strip.gsub(' ', '-').gsub(/[^\w-]/, '')
  id = ENV['id'] || title.downcase.strip.gsub(' ', '-').gsub(/[^\w-]/, '')
  subcat_of = ENV['subcat_of'] || ""

  if(subcat_of != "")
    FileUtils::mkdir_p File.join(CONFIG['categories'], "#{subcat_of}/#{id}")
    filename = File.join(CONFIG['categories'], "#{subcat_of}/#{id}/index.#{CONFIG['post_ext']}")
  else
    FileUtils::mkdir_p File.join(CONFIG['categories'], "#{id}")
    filename = File.join(CONFIG['categories'], "#{id}/index.#{CONFIG['post_ext']}")
  end

  if(File.exist?(filename))
    abort("rake aborted") if ask("#{filename} already exists. Overwrite?", ['y', 'n']) == 'n'
  end

  puts "Creating new category: #{filename}."

  open(filename, 'w') do |category|
    category.puts "---"
    category.puts "layout: post"
    category.puts "title: #{title}"
    category.puts "category: #{id}"
    category.puts "---"
    category.puts ""
    category.puts "{% include category.html param = page.layout %}"
  end

  puts "Category '#{title}' has been successfully created!"

end

# Usage: rake post title="Title" [date="2017-01-13"] [category="category"]
# remove []! this is only to say that these fields are optional.
# By default, every post's commenting functionality will be on. Change if necessary.
desc "Begin a new post in #{CONFIG['posts']}"
task :post do
  abort("rake aborted: '#{CONFIG['posts']}' directory not found.") unless FileTest.directory?(CONFIG['posts'])

  title = ENV["title"] || "new-post"
  category = ENV["category"] || ""
  slug = title.downcase.strip.gsub(' ', '-').gsub(/[^\w-]/, '')

  begin
    date = ( ENV['date'] ? Time.parse(ENV['date']) : Time.now).strftime('%Y-%m-%d')
  rescue => e
    puts "Error: date format must be YYYY-MM-DD, please check it once more"
    exit -1
  end

  filename = File.join(CONFIG['posts'], "#{date}-#{slug}.#{CONFIG['post_ext']}")

  if(File.exist?(filename))
    abort("rake aborted") if ask("#{filename} already exists. Overwrite?", ['y', 'n']) == 'n'
  end

  puts "Creating new post: #{filename}."

  open(filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: post"
    post.puts "title: \"#{title.gsub(/-/, ' ')}\""
    post.puts "category: #{category}"
    post.puts "date: #{date}"
    post.puts "comments: true"
    post.puts "disqus_identifier: #{SecureRandom.hex(8)}"
    post.puts "highlights: false"
    post.puts "---"
  end

  puts "Post '#{title}' has been successfully created!"

end

=begin

  Common Functions

=end

# asking user for further options
def ask(message, valid_options)
  if valid_options
    answer = get_stdin("#{message} #{valid_options.to_s.gsub(/"/, '').gsub(/, /,'/')} ") while !valid_options.include?(answer)
  else
    answer = get_stdin(message)
  end
  answer
end

def get_stdin(message)
  print message
  STDIN.gets.chomp
end
