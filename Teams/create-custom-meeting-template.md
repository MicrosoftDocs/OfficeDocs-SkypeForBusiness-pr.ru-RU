---
title: Создание пользовательского шаблона собрания в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Узнайте, как администраторы Microsoft Teams могут создать пользовательский шаблон собрания, чтобы задать или применить параметры организатора собрания для повышения безопасности и соответствия требованиям.
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800269"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>Создание пользовательского шаблона собрания в Microsoft Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Настраиваемые шаблоны собраний Microsoft Teams (функция Teams премиум) позволяют указать значения для многих параметров собрания, доступных организаторам собраний. Шаблоны могут настраивать параметры, которые организаторы собраний могут изменять, или блокировать параметры, чтобы организаторы собрания не могли их изменить. Дополнительные сведения о пользовательских шаблонах собраний см. [в статье Обзор пользовательских шаблонов собраний в Microsoft Teams](custom-meeting-templates-overview.md).

Можно создать до 50 пользовательских шаблонов. Сведения о том, как управлять шаблонами собраний, доступными для пользователей, см. [в статье Управление шаблонами собраний в Microsoft Teams](manage-meeting-templates.md) .

Для каждого параметра в шаблоне можно определить следующее:

- **Значение по умолчанию** — это значение, которое применяется к собранию при использовании шаблона.
- **Видимый** — определяет, может ли организатор собрания видеть этот параметр в параметрах собрания. 
- **Состояние блокировки** — определяет, может ли организатор собрания изменить параметр, заданный шаблоном. Если параметр заблокирован, организатор собрания не сможет его изменить.

Создание пользовательского шаблона собрания

1. В Центре администрирования Teams разверните узел **Собрания** и выберите **Шаблоны собраний**.
1. Выберите **Добавить.**
1. Введите имя и описание шаблона.
1. Выберите параметры, которые нужно использовать для этого шаблона. (Описание каждого параметра см. в разделах ниже.)
1. Чтобы предотвратить изменение параметра организатором собрания, выберите параметр, а затем нажмите **заблокировать**.
1. Чтобы организатор собрания не видел параметр, выберите параметр и нажмите **кнопку Скрыть**.
1. Нажмите **Сохранить**.

После создания шаблона может потребоваться до 24 часов, чтобы быть доступным для пользователей.

#### <a name="security"></a>Безопасность

|Параметр|Описание|
|:------|:----------|
|Метка конфиденциальности|Указывает метку конфиденциальности собрания, которая будет использоваться для собрания. Обратите внимание, что метка конфиденциальности может переопределять определенные параметры в шаблоне.|
|Кто может обойти лобби?|Указывает, кто может обойти лобби и присоединиться к собранию напрямую.|
|Люди при звонке в можно обойти лобби|Указывает, могут ли люди, звоня по телефону, обходить зал ожидания и присоединяться к собранию напрямую.|
|Уведомление о присоединении абонентов и выходе из нее|Укажите, должен ли звук воспроизводиться, когда люди, звоня по телефону, присоединяются к собранию или покидают его.|
|Включение сквозного шифрования собраний|Укажите, будет ли собрание использовать сквозное шифрование. Запись и транскрибирование не будут работать, если она включена.|
|Применение подложки к общему содержимому|Указывает, накладывается ли подложка на содержимое, которое предоставляется на экране собрания.|
|Применение водяного знака к видеопотоку всех пользователей|Указывает, накладывается ли подложка на видеопотоки участников собрания.|

#### <a name="audio-and-video"></a>Аудио и видео

|Параметр|Описание|
|:------|:----------|
|Разрешить микрофон для участников|Если **включено**, участники могут включить ввод.|
|Разрешить камеру для участников|Если **включено**, участники могут включить свои камеры.|

#### <a name="recording-and-transcription"></a>Запись и транскрибирование

|Параметр|Описание|
|:------|:----------|
|Автоматическая запись собраний|**Если собрания** On записываются автоматически.|
|Кто может записывать собрания?|Указывает, могут ли собрания записываться только организаторами или организаторами и выступающими.|

#### <a name="meeting-engagement"></a>Участие в собрании

|Параметр|Описание|
|:------|:----------|
|Участники могут общаться в чате|Указывает, доступен ли чат собрания. Также можно использовать для предотвращения чата до и после собрания.|
|Участники могут использовать реакции|Указывает, могут ли участники использовать реакции в собрании. Это значение должно быть **включено** , чтобы функция поднятия руки работала.|
|Включение Q&A|Указывает, могут ли участники использовать функцию Q&A, чтобы задавать вопросы во время собрания.|
|Управление тем, что видят участники|Когда **включено**, организаторы собрания могут просматривать и утверждать содержимое, к которым предоставляется общий доступ на экране, прежде чем другие участники собрания смогут увидеть его.|

## <a name="related-topics"></a>См. также

[Обзор пользовательских шаблонов собраний в Microsoft Teams](custom-meeting-templates-overview.md)

[Совместное использование шаблонов собраний Teams, меток конфиденциальности и политик администрирования](meeting-templates-sensitivity-labels-policies.md)

[Настройка собраний Teams с тремя уровнями защиты](configure-meetings-three-tiers-protection.md)