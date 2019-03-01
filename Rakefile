class String
  def shuffle
    split('').shuffle.join
  end

  def shuffle!
    replace shuffle
  end
end

task :default do
  system "echo Rake tasks"
  system "rake --tasks"
end

desc 'Generate an obfuscated email address to stop spammers'
task :email do
  puts 'Please type in an email address then press ENTER/RETURN'
  address = STDIN.gets.chomp.downcase
  key = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789'
  key.shuffle!
  puts "\nInstallation:\nUpdate src/_config.yml with the following pairs.\n\nemail-key: #{key}"

  scrambled = ''
  shift = address.length
  (0..shift-1).each do |i|
    if key.index(address[i]) == nil
  		scrambled += address[i]
    else
      chr = (key.index(address[i]) + shift) % key.length
  		scrambled += key[chr]
    end
  end
  puts "email-encoded: #{scrambled}\n"
end
