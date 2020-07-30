---
title: Использование NDI в Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как использовать NDI в Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522919"
---
# <a name="use-ndi-in-microsoft-teams"></a>Использование NDI в Microsoft Teams

[!INCLUDE [template](includes/preview-feature.md)]

Интерфейс сетевых устройств (NDI) — это современное решение для подключения устройств мультимедиа (например, камеры и микшера Studio). Вместо использования физических подключений NDI включает подключение через локальную интрасеть, в том числе на локальном компьютере.

NewTek NDI® стала стандартным отраслевым решением для создания живого содержимого для потоков и значительной осведомленности и внедрения в мир широковещательных кадров профессионального качества.

Ранее вы добавили в Skype 2018 функцию NDI. Microsoft Teams использует эти функции для повышения эффективности собраний.

NDI ограничен в локальной сети, и его следует считать только частью рабочего процесса, а не широковещательным решением.

## <a name="turn-on-ndi"></a>Включение NDI

NDI требует, чтобы пользователь включил два действия.

1. Администратор клиента должен включить функцию Flag enableStreamingCallsOverNdi.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. После того как это изменение будет заполнено, конечный пользователь должен включить NDI для определенного клиента из разрешений на **Параметры**  >  **Permissions**.

Когда пользователь присоединяется к собранию, он увидит сообщение с уведомлением о том, что собрание пересылается. Если вы не хотите, чтобы пользователи были включены в вещание, они должны будут перетаскиваться с собрания.

На приведенном ниже рисунке показано сообщение с рекламой, которое пользователь видит в собрании Teams.

![Изображение баннера NDI, которое отображается в собрании Teams.](media/NDI-disclosure.png)

Баннер содержит ссылку на [политику конфиденциальности Майкрософт](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).

## <a name="supported-locales-and-user-types"></a>Поддерживаемые национальные настройки и пользовательские типы

NDI поддерживается всеми языками. В собрании NDI поддерживаются следующие пользователи:

- Полная поддержка в клиенте, доставленная на основе звонков/tenantId/userId (в соответствии с политикой собраний + флагом функции)
- Федеративная – нет (даже если у них NDI на)<sup>1</sup>
- Freemium-No (значение по умолчанию)
- Анонимный – нет (значение по умолчанию)
- Гость – нет (значение по умолчанию)

по умолчанию для <sup>1</sup> устройств ЗАДАН параметр NDI. Если участник собрания использует устройство с NDI, необходимо включить NDI.
