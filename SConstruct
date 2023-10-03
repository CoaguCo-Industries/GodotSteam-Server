#!python
import os

def configure(env):
    from SCons.Script import BoolVariable, EnumVariable, Variables, Help

    env_vars = Variables()

    env_vars.Add("br_cc",
    "Set CC to use", env['CC'])

    env_vars.Add("br_cxx",
    "Set CXX to use", env['CXX'])

    env_vars.Update(env)
    Help(env_vars.GenerateHelpText(env))

opts = Variables([], ARGUMENTS)

# Gets the standard flags CC, CCX, etc.
env = SConscript("godot-cpp/SConstruct")

configure(env)
env['CC'] = env['br_cc']
env['CXX'] = env['br_cxx']

# Define our options
opts.Add(PathVariable('target_path', 'The path where the lib is installed.', 'bin/'))
opts.Add(PathVariable('target_name', 'The library name.', 'godotsteam_server', PathVariable.PathAccept))

# Local dependency paths, adapt them to your setup
steam_lib_path = "godotsteam_server/sdk/redistributable_bin"

# Updates the environment with the option variables.
opts.Update(env)

# For the reference:
# - CCFLAGS are compilation flags shared between C and C++
# - CFLAGS are for C-specific compilation flags
# - CXXFLAGS are for C++-specific compilation flags
# - CPPFLAGS are for pre-processor flags
# - CPPDEFINES are for pre-processor defines
# - LINKFLAGS are for linking flags

# Check our platform specifics
if env['platform'] == "osx":
    # Set the correct Steam library
    steam_lib_path += "/osx"
    steamworks_library = 'libsteam_api.dylib'

elif env['platform'] in ('linuxbsd', 'linux'):
    # Set correct Steam library
    steam_lib_path += "/linux64"
    steamworks_library = 'libsteam_api.so'

elif env['platform'] == "windows":
    # This makes sure to keep the session environment variables on windows,
    # that way you can run scons in a vs 2017 prompt and it will find all the required tools
    # env.Append(ENV=os.environ)

    # Set correct Steam library
    steam_lib_path += "/win64"
    steamworks_library = 'steam_api64.dll'

# make sure our binding library is properly includes
env.Append(LIBPATH=[steam_lib_path])
env.Append(CPPPATH=['godotsteam_server/sdk/public'])
env.Append(LIBS=[
    steamworks_library.replace(".dll", "")
])

# tweak this if you want to use different folders, or more folders, to store your source code in.
env.Append(CPPPATH=['godotsteam_server/'])
sources = Glob('godotsteam_server/*.cpp')

library = env.SharedLibrary(target=env['target_path'] + env['target_name'] + env["suffix"] + env["SHLIBSUFFIX"], source=sources)
env.Depends(library, Command("bin/" + steamworks_library, steam_lib_path + "/" + steamworks_library, Copy("$TARGET", "$SOURCE")))

Default(library)

# Generates help for the -h scons option.
Help(opts.GenerateHelpText(env))