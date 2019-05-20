# samp-map-editor
Инструкция по сборке:
1. Скачайте и установите **Borland Delphi 7**
2. Скачайте и скомпилируйте компоненты (см. ниже)
3. Склонируйте репозиторий:
```
git clone https://github.com/vsergeenko777/samp-map-editor.git
```
4. Откройте проект **samp-map-editor/editor.dpr** через Borland Delphi 7
5. Нажмите **Ctrl+F9** (или Project -> Compile editor), компиляция должна завершиться успешно
6. В папке проекта появится исполняемый файл **editor.exe**, дополните его DLL (GTAINTERFACE.dll и newton.dll) и попробуйте запустить
### Компоненты
Скачайте необходимые компоненты:
* [GLScene 1.0.0.0714](https://sourceforge.net/projects/glscene/files/GLScene/GLScene%20v1.0.0.0714/glscene_v_1000714_delphi7_full.7z/download)
* [SynEdit 2.1.0](https://github.com/SynEdit/SynEdit/archive/SynEdit-2.1.0-beta.zip)

Компиляция GLScene:
1. Распакуйте файлы из папки **GLScene_v100** в архиве в любое место, например в **C:\GLScene**
2. Откройте проект **C:\GLScene\Delphi7\Delphi7.bpg** через Borland Delphi 7, проигнорируйте ошибки про .res файлы
3. Откройте **Enviroment Options (Tools -> Enviroment Options)**, перейдите во вкладку **Library**
4. Нажмите кнопку **"..."** напротив **Library path**
5. По очереди добавьте все пути к исходникам GLScene, используя **"..."**, чтобы выбрать папку и кнопку **Add**, чтобы добавить путь, по итогу должен быть такой список:
```
C:\GLScene\Source
C:\GLScene\Source\Base
C:\GLScene\Source\CgShaders
C:\GLScene\Source\DesignTime
C:\GLScene\Source\FileFormats
C:\GLScene\Source\GameAPIs
C:\GLScene\Source\PhysicsAPIs
C:\GLScene\Source\Platform
C:\GLScene\Source\PlugIn
C:\GLScene\Source\ScriptingAPIs
C:\GLScene\Source\Shaders
C:\GLScene\Source\SoundAPIs
C:\GLScene\Source\VideoAPIs
```
6. В окне **Project Manager** (должно было появиться после открытия проекта), выберите **GLScene7.bpl**, нажмите **Activate**
7. Кликните ПКМ по **GLScene7.bpl** и нажмите **Build**
8. Возможно, при компиляции появится ошибка **File not found: 'Info.res'**, откройте файл **Info.pas** и удалите строку **{$R Info.res}**, снова нажмите **Build**
9. Если компиляция завершилась успешно, нажмите **Install** в том же меню (ПКМ по GLScene7.bpl)
10. Проект можно закрыть, сохраняя или не сохраняя - без разницы

Компиляция SynEdit:
1. Распакуйте файлы из папки **SynEdit-SynEdit-2.1.0-beta** в архиве в любое место, например в **C:\SynEdit**
2. Откройте проект **C:\SynEdit\Packages\D7\SynEdit_R7.dpk** (именно **R7**) через Borland Delphi 7, проигнорируйте ошибку про .res файл
3. В окне **Package - SynEdit_R7.dpk** нажмите Compile
4. Возможно, при компиляции появится ошибка про неожиданные символы в файле **SynHighlighterJava.pas**, удалите их (в начале файла, до фигурной скобки) и попробуйте скомпилировать ещё раз
5. Если компиляция завершилась успешно, закройте проект
6. Откройте проект **C:\SynEdit\Packages\D7\SynEdit_D7.dpk** (именно **D7**), снова проигнорируйте ошибку про .res файл
7. В окне **Package - SynEdit_D7.dpk** нажмите Compile
8. Снова откройте **Enviroment Options** (как в инструкции выше), перейдите в **Library**, откройте **Library path** и добавьте путь **C:\SynEdit\Source**
9. Проект можно закрыть, сохраняя или не сохраняя - без разницы
