task "create", [:server_name] do |t, args|
  unless ENV['DIGITAL_OCEAN_KEY']
    puts "You need to set a export an API token as DIGITAL_OCEAN_KEY"
    exit 1
  end

  unless ENV['DIGITAL_OCEAN_SSH_KEYS']
    puts "You need to set a export a list of key ids as DIGITAL_OCEAN_SSH_KEYS'"
    exit 1
  end

  if args[:server_name].nil?
    puts "Missing a name for the new droplet"
    exit 1
  end

  keys = ENV['DIGITAL_OCEAN_SSH_KEYS']

  cmd = "knife digital_ocean droplet create -N #{args[:server_name]} -S 1gb -L nyc3 -I ubuntu-14-04-x64 -K #{keys} --solo --run-list 'role[node]'"
  puts cmd
end
