# frozen_string_literal: true

REFERENCE_LANGUAGE = 'en'
MAXIMUM_KEYWORDS_LENGTH = 100

# TODO:
# - [ ] Validate keywords
# - [ ] Ensure description isn’t empty
# - [ ] Ensure all of the reference languages’s keys are present for a given strings file

desc 'Validate strings'
task :test do
  @errors = 0

  # Check for reference language
  reference_language_path = "#{REFERENCE_LANGUAGE}.lproj"
  unless Dir.exists? reference_language_path
    abort("❌  Missing reference language: #{reference_language_path}")
  end

  # Get reference language files list
  reference_files = Dir.chdir(reference_language_path) do
    Dir['*']
  end

  # Find additional languages
  languages = Dir['*.lproj'].reject { |path| path == reference_language_path }
  puts "ℹ️  Checking #{languages.join(', ')}"

  # Check each language
  languages.each do |language|
    # Check each file
    reference_files.each do |file|
      path = "#{language}/#{file}"

      # Ensure file exists
      unless File.exists? path
        error "Missing file: #{path}"
        next
      end

      # If it's a .strings file, validate it
      if File.extname(path) == '.strings'
        system("plutil -lint '#{path}'")
        unless $?.exitstatus == 0
          error "nvalid strings file: #{path}"
        end
      end
    end
  end

  puts

  if @errors == 0
    puts '✅  Success!'
  else
    abort "❌  #{@errors} error#{@errors == 1 ? '' : 's'}."
  end
end

task default: :test

private

def error(message)
  @errors += 1
  puts "❌  #{message}"
end
