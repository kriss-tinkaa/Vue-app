<template>
<v-card color="basil">
    <v-card-title class="text-center justify-center py-6">
      <h1 class="font-weight-bold display-3 basil--text">
        The Best Website to Learn English
      </h1>
    </v-card-title>

    <v-tabs
      v-model="tab"
      background-color="transparent"
      color="basil"
      grow
    >
      <v-tab :key="1">
        Sites
      </v-tab>
      <v-tab :key="2">
        Apps
      </v-tab>
       <v-tab-item :key="1">
        <v-card 
          color="basil"
          flat>
          <v-card-text>
            <ol>
                <li><a href="http://learnenglish.britishcouncil.org/en/" target="_blank" rel="nofollow">British Council</a> – хаб с разными уроками, видео и играми который подойдет как детям, так и взрослым</li>
                <li><a href="http://livemocha.com/" target="_blank" rel="nofollow">Livemocha</a> – бесплатный сайт для (иногда бесплатного) общения с носителями английского языка. Пожалуй, лучший способ развивать speaking</li>
                <li>
                    <a href="http://easyworldofenglish.com/" target="_blank" rel="nofollow">Easy World of English</a> – сайт с максимально доступным интерфейсом который включает уроки по грамматике, произношению, чтению текстов на
                    английском языке (+ многое другое)
                </li>
                <li><a href="http://www.manythings.org/" target="_blank" rel="nofollow">Many Things</a> – сайт включает в себя игры и другие интерактивные способы полноценного развития английского языка</li>
                <li><a href="https://puzzle-english.com/" target="_blank" rel="nofollow">Puzzle English</a> – еще один сайт для интерактивного и интенсивного изучения английского языка</li>
            </ol>
            <v-divider></v-divider>
            <h3>Видео ресурсы</h3>
            <ol>
                <li><a href="http://ted.com/" target="_blank" rel="nofollow">TED talks</a> – разные выступления на различные темы. Видео сопровождаются субтитрами и транскритами</li>
                <li><a href="http://www.elllo.org/" target="_blank" rel="nofollow">ello</a> – всевозможные видео + подкасты</li>
                <li><a href="http://englsecrets.ru/videouroki" target="_blank" rel="nofollow">Секреты английского языка</a> – видео и упражнения для изучения английского языка</li>
                <li><a href="http://english03.ru/video-uroki" target="_blank" rel="nofollow">Английский язык по красному Мерфи</a> – видео, упражнения, разговорник и многое другое</li>
                <li><a href="http://www.delightenglish.ru/Videocurs.htm" target="_blank" rel="nofollow">DelightEnglish</a> – тематические видеоуроки по разговорному английскому</li>
                <li><a href="http://americanenglish.ua/video-uroki/video-uroki/blog.html" target="_blank" rel="nofollow">American English Center</a> – видеуроки на разные топики по грамматике</li>
            </ol>
            <v-divider></v-divider>
            <h3>Подкасты</h3>
            <ol>
                <li><a href="http://www.eslpod.com/website/index_new.html" target="_blank" rel="nofollow">ESL pod</a> – подкасты на совершенно разные, жизненные темы</li>
                <li>
                    <a href="http://www.ieltspodcast.com/ielts-vocabulary/087-fantastic-resource-improve-ielts-listening-speaking/" target="_blank" rel="nofollow">IELTS podcast</a> – подкаст для тех, кто активно готовится к этому
                    международному экзамену
                </li>
                <li><a href="http://www.podcastsinenglish.com/index.shtml" target="_blank" rel="nofollow">podcastsinenglish</a> – адаптированные подкасты, разделенные по уровням</li>
                <li><a href="http://www.englishclass101.com/" target="_blank" rel="nofollow">English Class 101</a> – уже упоминался в нашем первом посте</li>
                <li><a href="http://www.betteratenglish.com/" target="_blank" rel="nofollow">Better at English</a> – простые и понятные подкасты с транскриптами</li>
                <li><a href="http://www.betteratenglish.com/" target="_blank" rel="nofollow">PodOmatic</a> – подкасты для продвинутых</li>
                <li><a href="http://esl.culips.com/" target="_blank" rel="nofollow">CUlips</a> – подкасты на разные, в особенности, бытовые темы</li>
                <li><a href="http://teacherluke.co.uk/" target="_blank" rel="nofollow">Luke’s English podcast</a> – подкасты с британским акцентом + ваш помощник в развитии словарного запаса</li>
            </ol>        
          </v-card-text>
        </v-card>
      </v-tab-item>
       <v-tab-item :key="2">
        <v-card
          color="basil"
          flat>
          <v-card-text>
               <ol>
                <li><a href="https://www.duolingo.com/" target="_blank" rel="nofollow">Duolingo</a> – изучение английского с любого уровня, стилизованное под игру</li>
                <li><a href="https://lingualeo.com/chooselanguage?returnUrl=" target="_blank" rel="nofollow">LinguaLeo</a> – еще один “старожил” индустрии, больше подходит для детей</li>
                <li><a href="https://www.busuu.com/" target="_blank" rel="nofollow">Busuu</a> – очень эргономичное приложение для изучения&nbsp;<em>не</em> только английского языка</li>
                <li><a href="https://lingua.ly/" target="_blank" rel="nofollow">Lingua.ly</a> – особенность в том, что алгоритм программы подбирает тексты, соответствующие по сложности вашим текущим знаниям</li>
                <li>
                    <a href="https://play.google.com/store/apps/details?id=air.com.OSC.pattersEng" target="_blank" rel="nofollow">Carton Tongue Twister</a> – название говорит само за себя: с этим приложением вы будете оттачивать свое
                    произношение с помощью английских скороговорок
                </li>
                <li><a href="https://itunes.apple.com/ru/app/tykva-eng-ucim-anglijskij/id544693135?mt=8" target="_blank" rel="nofollow">Тыква Eng</a> – простой и понятный способ графического изучения грамматики английского языка</li>
                <li>
                    <a href="https://itunes.apple.com/ru/app/engcards/id842506942?mt=8" target="_blank" rel="nofollow">EngCards</a> – ваш надежный помощник при расширении словарного запаса путем использования
                    <a href="http://yvision.kz/post/527494" target="_blank">flashcards</a>
                </li>
                <li><a href="https://www.memrise.com/" target="_blank" rel="nofollow">Memrise</a> – проект международного краудсорсинга: карточки с изображением значений слов составляются пользователями, владеющими языком!</li>
                <li>
                    <a href="https://play.google.com/store/apps/details?id=air.org.cambridge.phrasalsteinlite&amp;hl=en" target="_blank" rel="nofollow">Phrasalstein</a> – специализированное приложение для изучения именно phrasal verbs
                    (важный аспект при изучении англгийского языка, т.к. нет аналогии в казахском/русском)
                </li>
                <li><a href="http://www.easyten.ru/en" target="_blank" rel="nofollow">Easy ten</a> – всего по 10 слов каждый день может позволить себе каждый!</li>
                <li><a href="https://itunes.apple.com/us/app/ef-mywords-english/id393088047?mt=8" target="_blank" rel="nofollow">EF MyWords</a> – комплексное расширение вашего словарного запаса (карточки, текст, аудио)</li>
                <li><a href="http://polyglotmobile.ru/" target="_blank" rel="nofollow">Полиглот</a> – современное приложение для желающих изучать английский язык в олдскульном формате</li>
                <li>
                    <a href="https://play.google.com/store/apps/details?id=com.funeasylearn.english&amp;hl=en" target="_blank" rel="nofollow">Learn English 6000 Words</a> – еще одно интересное приложение для изучения английских слов
                    путем распознавания картинок
                </li>
                <li><a href="https://play.google.com/store/apps/details?id=com.intriga_games.intrigaenglishteacher" target="_blank" rel="nofollow">Английский язык by INTRIGA-games</a> – изучение грамматики тестовым способом</li>
                <li><a href="https://play.google.com/store/apps/details?id=english.grammar.test.app&amp;hl=en" target="_blank" rel="nofollow">English Grammar Test</a> – 1200 вопросов по грамматике английского языка</li>
                <li><a href="https://play.google.com/store/apps/details?id=talkenglish.com.standard&amp;hl=en" target="_blank" rel="nofollow">Learn to Speak English</a> – 900 уроков и 8000 аудиофайлов точно помогут вам в изучении</li>
                <li>
                    <a href="https://play.google.com/store/apps/details?id=vn.scdgroup.bbclearningenglish&amp;hl=en" target="_blank" rel="nofollow">6 Minute English Listening</a> – один из лучших способов развить навыки listening от BBC
                </li>
                <li>
                    <a
                        href="https://play.google.com/store/apps/developer?id=speakASAP.com+-+%D0%9E%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD+%D0%BE%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5+%D0%B8%D0%BD%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC+%D1%8F%D0%B7%D1%8B%D0%BA%D0%B0%D0%BC&amp;hl=en"
                        target="_blank"
                        rel="nofollow"
                    >
                        Speak ASAP
                    </a>
                    – уроки разговорного английского языка для русскоговорящих
                </li>
                <li>
                    <a href="https://play.google.com/store/apps/details?id=com.coderzheaven.englishtenses&amp;hl=en" target="_blank" rel="nofollow">English Tenses</a> – еще одно профильное приложение для изучения времен английского
                    языка
                </li>
            </ol>
         </v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs>
  </v-card>
    
</template>
