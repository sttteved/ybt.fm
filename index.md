---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
---

<iframe width="100%" height="165" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/users/167903027&color=%23d8ec44&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe>

<div class="btn__container">
  <a class="btn itunes" href="https://itunes.apple.com/us/podcast/yall-boys-talkin/id1452781895?mt=2">iTunes</a>
  <a class="btn play" href="https://play.google.com/music/listen#/ps/Icqw2qixlfgyrebhomlxrhen7k4">Google Play</a>
  <a class="btn spotify" href="https://open.spotify.com/show/5xzMcpzL8T5g7zGqNMoQcB?si=zEyr_F4oQs6El1av3kT8iA&fbclid=IwAR3i67W65XU4Fl8HpIduxKlhzVsPwT2XP3a6vbxKc2WYUUF-SCXfPzHRWIc">Spotify</a>
  <a class="btn rss" href="/feed/">Podcast RSS</a>
</div>

<style scoped>
a,
a:hover,
a:visited {
  color: currentColor;
}

.btn__container {
  display: flex;
  width: 100%;
  margin: 2em 0;
}

.btn {
  box-shadow: 0 0 0 2px inset;
  padding: .5em;
  flex: 1;
  text-align: center;
  font-weight: 500;
  font-size: 0.8em;
  text-transform: uppercase;
  margin-right: 1em;
}

a.btn:hover {
  box-shadow: none;
  text-decoration: none;
  color: white;
}

.btn:last-child {
  margin-right: 0;
}

a.itunes {
  color: #ef6754;
}

a.itunes:hover {
  background: #ef6754;
}

a.play {
  color: #ff4f2d;
}

a.play:hover {
  background: #ff4f2d;
}

a.rss {
  color: #f26522;
}

a.rss:hover {
  background: #f26522;
}

a.spotify {
  color: #1db954;
}

a.spotify:hover {
  background: #1db954;
}

a.disabled,
a.disabled:visited,
a.disabled:hover {
  box-shadow: 0 0 0 2px inset;
  color: #999;
  opacity: .25;
  background: initial;
  cursor: not-allowed;
}

@media only screen and (max-width: 768px) {
  .btn__container {
    flex-flow: column;
  }

  .btn {
    margin-right: 0;
    margin-bottom: 1em;
  }
}
</style>