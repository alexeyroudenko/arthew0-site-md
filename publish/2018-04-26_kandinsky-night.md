---
layout: post
title: «Ночь Кандинского» в Третьяковской галерее на Крымском Валу
date: 2018-04-26 06:13:15+00:00
categories: audiovisual computervision openframeworks forms
---
<h2 class="p1"><div class="video-responsive"><iframe width="100%" height="350" src="https://player.vimeo.com/video/167339336" frameborder="0" webkitallowfullscreen="webkitallowfullscreen" mozallowfullscreen="mozallowfullscreen" allowfullscreen="allowfullscreen"></iframe></div></h2>
<p class="p1"><span class="s1">Работа над официальным тизером спецпроекта &laquo;Ночь Кандинского&raquo;. </span></p>
<p></p>
<p>Данный тизер был выполнен &nbsp;в виде аудиовизуальной композиции, которая записывалась с экрана в реальном времени.</p>
<p>Использованные технологии : openframeworks, glsl, midi, opencv, ableton</p>
<p><br /><br /><br /></p>
<h3>Сценарий</h3>
<p>Композиция в Ableton кроме аудиопотока&nbsp;управляет сценарием, посылая midi-сигналы</p>
<p><a href="/media/uploads/kn/01_kn_ableton.png" title="ableton composition"><img src="/media/uploads/kn/01_kn_ableton.png" width="100%" /></a></p>
<p><br /><br /></p>
<h3>Звучание форм :: Трекинг</h3>
<p><i>&laquo;Сама форма, даже если она совершенно абстрактна и подобна геометрической, имеет свое внутреннее звучание, является духовным существом с качествами, которые идентичны с этой формой&raquo;.</i></p>
<p></p>
<div align="right">В. В. Кандинский &ndash;&nbsp;<a href="http://www.e-reading.club/chapter.php/150067/14/Kandinskiii_-_O_duhovnom_v_iskusstve.html">О духовном в искусстве</a></div>
<p>Кроме управляющего сценария в инструменте для написания музыки, &nbsp;дополнительно существует&nbsp;обратная связь - анализируемая картина просит Ableton проиграть&nbsp;найденные контуры. Кратко: анализ картины компьютерным зрением, поиск форм в виде чб-контуров.</p>
<p><a href="/media/uploads/kn/kn.png" title="composition architecture"><img src="/media/uploads/kn/kn.png" width="100%" /></a></p>
<p></p>
<p><br /><br /><br /></p>
<h3>Инструментарий:</h3>
<p>Так выглядит исходный код визуальной части. Уровень абстракции&nbsp;инструмента, с помощью которого достигается цель достаточно велик, не так много использовано готовых решений, работа сама по себе является этапом исследования и развития в этом направлении.</p>
<p><img src="/media/uploads/kn/06_kn.png" width="100%" /></p>
<p><br /><br /></p>
<p></p>
<h3>Найденные формы:</h3>
<p><a href="/media/uploads/kn/02_kn_tracking_01.png"><img src="/media/uploads/kn/02_kn_tracking_01.png" width="100%" /></a></p>
<p>Словно иглой винилового проигрователя, проигрывание форм картины следует&nbsp;из анализа цвета конкретной точки (показано кружочками) и поиск областей с полученным оттенком</p>
<p><a alt="" href="/media/uploads/kn/03_tracking_02.jpg" width="500"><img alt="color flow map" src="/media/uploads/kn/03_tracking_02.jpg" width="100%" /></a></p>
<p><br /><br /><br /></p>
<h3>Движение цвета</h3>
<p>Ниже приведена цитата из произведения Василия Кандинского касаемо &laquo;восприятия цвета&raquo;. Смею заметить, что это не совсем области захватывающие&nbsp;синтестезию, и в этом я нахожу особую значимость его размышлений. Это скорей ближе к законам восприятия, которые очень вероятно окажутся равными для всех.</p>
<blockquote>
<p><em><span class="s1">&laquo;Второго рода движение: желтого и синего, усиливающее первый большой контраст, есть их эксцентрическое или концентрическое движение.* Если нарисовать два круга одинаковой величины и закрасить один желтым, а другой синим цветом, то уже при непродолжительном сосредоточивании на этих кругах можно заметить, что желтый круг излучает, приобретает движение от центра и почти видимо приближается к человеку, тогда как синий круг приобретает концентрическое движение (подобно улитке, заползающей в свою раковину) и удаляется от человека. Первый круг как бы пронзает глаза, в то время как во второй круг глаз как бы погружается.&raquo;</span></em></p>
<p class="p1" style="text-align: right;"><span class="s1">Василий Кандинский &laquo;О духовном в искусстве&raquo;</span></p>
</blockquote>
<p>Часть с движением цвета реализованно glsl шейдерами. Данная&nbsp;техника зачастую используется в компьютерных играх для анимации поверхности воды. Каждая точка цвета в данной карте это по сути вектор с направлением и инстенсивностью движения.</p>
<p><img alt="" height="151" src="/media/uploads/kn/200px-water_flow_test.png" width="151" /></p>
<p>Была создана на c++&nbsp;и openframeworks утилита, для рисования данных карт:</p>
<p><a href="/media/uploads/kn/05_kn_flow.jpg"><img src="/media/uploads/kn/05_kn_flow.jpg" width="100%" /></a></p>
<p>Утилита для работы с картами Flow Map:&nbsp;<a href="http://arthew0.ru/cc/apps/kandinsky_color_flow_0.1.zip">kandinsky_color_flow_0.1.zip</a>&nbsp;дает результат:</p>
<p></p>
<p>А так же исходный код выложен в открытый доступ: <a href="https://github.com/alexeyroudenko/ofxColorFlow">https://github.com/alexeyroudenko/ofxColorFlow</a><a href="https://github.com/alexeyroudenko/ofxColorFlow"></a></p>
<p>Работа является по сути результатом многочисленных экспериментов с анализом изображений, синтезом звука, описаных в проекте&nbsp;<a href="http://arthew0.ru/forms/">http://arthew0.ru/forms/</a></p>