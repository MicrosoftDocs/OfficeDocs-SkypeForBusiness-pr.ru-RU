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
description: Узнайте, как использовать NDI в Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337018"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Использование NDI® в Microsoft Teams

 Технология NewTek NDI® (Network Device Interface) — это современное решение для подключения медиа устройств (например, студийной камеры и mixer). Вместо физических подключений технология NDI® обеспечивает подключение к локальной интрасети, в том числе на локальном компьютере.

Технология NDI® стала стандартным отраслевым решением для создания трансляций контента для потоков и стала более заметной в профессиональном мире широковещательного бизнеса.

Ранее Skype добавил функции ® NDI в Skype в конце 2018 г. Microsoft Teams использует эти функции для улучшения проведения собраний.

Технология NDI® ограничена локальной сетью и должна рассматриваться только как часть рабочего процесса, а не решения для трансляции.

## <a name="turn-on-ndi-technology"></a>Включив технологию NDI®

Для ® NDI требуется два шага для того, чтобы пользователь включил ее.

1. Администратор клиента должен включить свойство AllowNDIStreaming в CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. После заполнения этого изменения конечный пользователь должен включить технологию NDI® для своего клиента в **параметрах**  >  **разрешений.**

Когда пользователь присоединяется к собранию, он видит сообщение о том, что собрание транслируется. Если пользователи не хотят включаться в трансляцию, им нужно будет отойди от собрания.

На следующем рисунке показано сообщение баннера, которое пользователь видит на собрании Teams.

![He NDI® technology banner that displays in a Teams meeting.](media/NDI-disclosure.png)

Баннер имеет ссылку на политику [конфиденциальности Майкрософт.](https://aka.ms/teamsprivacy)

## <a name="supported-locales-and-user-types"></a>Поддерживаемые региональные и пользовательские типы

NDI® поддерживается во всех региональных сфере. В поток NDI® NDI включаются следующие пользователи, но не все они могут получить доступ к ® NDI:

- Клиент — полная поддержка, которая доставляется на основе ring/tenantId/userId (управляется политикой собраний)
- Федерательный — без потокового доступа (даже если ® NDI)<sup>1</sup>
- Premium — без потокового доступа
- Анонимный доступ — нет потокового доступа
- Гость — нет потокового доступа  

<sup>На 1</sup> устройствах есть ® NDI, которая по умолчанию находится в режиме NDI. Если участник собрания использует устройство с выключенной технологией NDI®, он должен включить ® NDI.
