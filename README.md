# Unity Lightship Object Detection Template

Этот проект — **шаблон** для быстрого старта с [Niantic Lightship ARDK](https://lightship.dev/) и модулем **Object Detection**.  
Он основан на официальной документации и подходит для создания собственных AR-приложений с распознаванием объектов.

---

## Что внутри
- Базовая настройка **Lightship ARDK** в Unity.
- Конфигурированный `ARObjectDetectionManager`.
- Скрипт `LogResults` для логирования распознанных объектов в `Console`.
- Скрипты `DrawRect`, `ObjectDetectionSample`, `UIRectObject` для отображения текста и рамки вокруг распознанного объекта
- Проверено в **Android Build** и **Editor Playback**.

---

## 🚀 Как запустить

### Требования
- Unity **6000.1.12f1** или новее.
- Установленный **Lightship ARDK**.
- Поддерживаемый Android-устройство (API Level 24+).

### Шаги
1. Клонировать репозиторий.
2. Открыть проект в Unity.
3. Убедиться, что в сцене:
   * есть **XR Origin (AR)**,
   * на `Main Camera` добавлен `ARObjectDetectionManager`,
   * к объекту `ObjectDetectionLogic` прикреплён скрипт `LogResults`, в качестве `Object Detection Manager` в нем выбрана `Main Camera`.
   * к объекту `Canvas/BoundingBoxOverlay` прикреплен скрипт `DrawRect`, в качестве `Rectangle Prefab` в нем выбран `RectObject`.
   * к объекту `Sample` прикреплен скрипт `ObjectDetectionSample`, в качестве `Object Detection Manager` в нем выбрана `Main Camera`, в качестве `Draw Rect` в нем выбран `Canvas/BoundingBoxOverlay`.
   * ‼️*** Если какие-то объекты не прикреплены, проект работать не будет. ***‼️
4. Собрать проект на Android **или** протестировать через **Playback** в Editor.

---

## ⏰ Важное примечание

При **первом запуске** SDK пытается загрузить модель Object Detection с серверов Niantic.

* В регионах с ограничениями (например, Россия) может потребоваться **VPN**.
* После успешной загрузки модель кэшируется, и дальнейшая работа возможна офлайн (особенно на устройстве).

---

Этот проект можно использовать как шаблон, если заменить `LogResults`, `DrawRect`, `ObjectDetectionSample`, `UIRectObject` на собственную обработку результатов.
