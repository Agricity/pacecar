rails_versions = ['3.0.13', '3.1.5', '3.2.5']
database_drivers = ['mysql', 'pg', 'sqlite3']

rails_versions.each do |rails_version|
  database_drivers.each do |database_driver|
    appraise "rails-#{rails_version}-database-#{database_driver}" do
      gem 'rails', rails_version
      gem database_driver
      gem 'pacecar', :path => '../'
    end
  end
end

# The mysql2 gem needed by Rails changes with Rails versions
rails_to_mysql2_mappings = { '3.2.5' => '0.3.11', '3.1.5' => '0.3.11', '3.0.13' => '0.2.18' }
rails_to_mysql2_mappings.each do |rails_gem_version, mysql2_gem_version|
  appraise "rails-#{rails_gem_version}-database-mysql2" do
    gem 'rails', rails_gem_version
    gem 'mysql2', mysql2_gem_version
    gem 'pacecar', :path => '../'
  end
end
