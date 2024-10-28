class MusicPlayer:
                print("Playing:", self.playlist[self.current_song_index])
                self.paused = False
            elif choice == '2':
                print("Paused:", self.playlist[self.current_song_index])
                self.paused = True
            elif choice == '3':
                self.current_song_index += 1
                if self.current_song_index >= len(self.playlist):
                    print("End of playlist")
                    break
                else:
                    print("Skipping to next song:", self.playlist[self.current_song_index])
            elif choice == '4':
                new_song = input("Enter the name of the next song to add to the playlist: ")
                self.add_song(new_song)
            elif choice == '5':
                print("Exiting music player.")
                break
            else:
                print("Invalid choice")

def main():
    player = MusicPlayer()
    while True:
        song = input("Enter the name of the song to add to the playlist (or 'exit' to start the player): ")
        if song.lower() == 'exit':
            break
        player.add_song(song)
    player.play()

if __name__ == "__main__":
    main()
