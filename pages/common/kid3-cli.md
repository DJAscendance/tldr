# kid3-cli

> Command-line tagger for Kid3, an audio tag editor.
> Operates on tag 1 (e.g. ID3v1), tag 2 (e.g. ID3v2, Vorbis, APE, MP4), and tag 3; reads tag 2 then 1, writes tag 2 by default.
> More information: <https://kid3.kde.org/>.

- Start interactive mode, opening a file or directory:

`kid3-cli {{path/to/file_or_directory}}`

- List the contents of a directory with tag and selection status:

`kid3-cli -c ls {{path/to/directory}}`

- Display all tag frames of an audio file:

`kid3-cli -c "get all" {{path/to/file.mp3}}`

- Display a specific tag frame (e.g. `artist`, `title`, `album`):

`kid3-cli -c "get {{frame_name}}" {{path/to/file.mp3}}`

- Set a tag frame's value (leave the value empty to delete the frame):

`kid3-cli -c "set {{frame_name}} '{{value}}'" {{path/to/file.mp3}}`

- Set tags from filenames using a format string:

`kid3-cli -c "totag '{{%{albumartist} - %{album}/%{track} %{title}}}' {{2}}" {{path/to/directory}}`

- Set filenames from tags using a format string:

`kid3-cli -c "fromtag '{{%{track} - %{title}}}' {{1}}" {{path/to/directory}}`

- Chain multiple commands (executed in order, then saved):

`kid3-cli -c "set artist '{{Artist}}'" -c "set album '{{Album}}'" {{path/to/directory}}`
