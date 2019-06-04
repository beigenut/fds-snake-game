<p align="center">
  <h3 align="center">fds-snake-game</h3>
  <p align="center">
  Develop a game that uses the keyboard to move the snake and to eat apples<br> 
  To check out the game?<a href="https://js-ex-02-snakegame.netlify.com/" target="_blank"> Click here</a> <br>
  You do not need to sign in or log in at this time :)
</p>
</p>

_ _ _

## Table of Contents

* [About the Project](#about-the-project)
  * [Built With](#built-with)
* [Usage](#usage)
* [Contributing](#contributing)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)

## About The Project

<img src="https://drive.google.com/uc?export=view&id=13RK72zHdqVyE9tjcWmEwQMuUxrb-6Su1" width="700px">

- All you need to do is eat the apple (the red dot) by avoiding hittig the bomb (the black doc). 
- Enjoy this easy-peasy-lemon-squeezy game. Good luck!


### Built With
* [snake game WIKI](https://en.wikipedia.org/wiki/Snake_%28video_game_genre%29)
* [Node install](https://github.com/coreybutler/nvm-windows)

이 프로젝트는 [뱀 게임](https://en.wikipedia.org/wiki/Snake_%28video_game_genre%29)의 로직을 쉽게 구현해볼 수 있도록, 기반 코드를 미리 작성해 놓은 템플릿 프로젝트입니다.

- 필요한 도구를 설치한 후 프로젝트를 실행시키세요.
- `src` 폴더 아래에 [SnakeGameLogic.js](./src/SnakeGameLogic.js) 파일을 편집하며 변화를 관찰해보세요.
- 뱀 게임이 제대로 동작할 수 있도록 SnakeGameLogic 생성자의 내부를 채워보세요.
- [config.js](./src/config.js) 설정 파일을 편집해보세요.

## Node 설치

- 버전 매니저 설치
  - Windows - [nvm-windows](https://github.com/coreybutler/nvm-windows)
  - macOS - [nvm](https://github.com/creationix/nvm) (설치 후 터미널 재시작)
- 아래 명령을 차례대로 실행
  - `nvm install 8.11.1`
  - `nvm use 8.11.1`

지금 당장 필요하지는 않으나 나중에 필요해질 수 있으므로 아래 도구들을 미리 설치하는 것이 좋습니다.

- Windows - [windows-build-tools](https://github.com/felixrieseberg/windows-build-tools)
- macOS - 터미널에서 `xcode-select --install` 실행

## 프로젝트 명령

- 프로젝트 의존성 설치
  - `npm install`
- 프로젝트 실행
  - `npm start`
- 프로젝트 빌드
  - `npm run build`

<!-- USAGE EXAMPLES -->
## Usage
The existing game rule was so simple; moving the snake to a apple cell. 

However, in order to boost the fun of the game playing, a `bomb` item is newly arranged. Player has to eat apple(s) avoiding the bomb. The game will be end when part of the snake's body touches.

- Game is over when snake hits a bomb

```js
// SnakeGameLogic.js
  function onBomb(position2, bomb) {  // position2 is snake's head
    if(position2.x === bomb.x && position2.y === bomb.y){
      return false;     // false ; game over
    }return true;
  }
```

Relocate the bomb When the snake touches the apple cell.

At this time, the newly drawn an apple and a bomb should not be drawn overlaped with each other and also should avoid of snake body.

```js
// SnakeGameLogic.js
function MakeThings(position1, body, object) {
  do{
    position1.x = Math.floor(Math.random() * COLS);
    position1.y = Math.floor(Math.random() * ROWS);   
  } while(onSnake(position1, body) || avoidOverlap(position1, object));
}

//...
MakeThings(this.fruit, this.joints, this.bomb);
MakeThings(this.bomb, this.joints, this.fruit);
```

<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- CONTACT -->
## Contact

Project Link: [https://github.com/beigenut/fds-snake-game](https://github.com/beigenut/fds-snake-game)



## Acknowledgements
* [snake game WIKI](https://en.wikipedia.org/wiki/Snake_%28video_game_genre%29)