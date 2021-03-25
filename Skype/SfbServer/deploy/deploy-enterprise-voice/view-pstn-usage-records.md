---
title: Просмотр записей использования PSTN в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: Сводка. Узнайте, как просматривать записи использования PSTN с помощью панели управления Skype для бизнес-серверов или оболочки управления Skype для бизнес-серверов.
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109835"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Просмотр записей использования PSTN в Skype для бизнеса

**Сводка:** Узнайте, как просматривать записи использования PSTN с помощью панели управления Skype для бизнес-серверов или оболочки управления Skype для бизнес-серверов.

Запись использования общедоступных переключений телефонной сети (PSTN) указывает класс вызова (например, внутренний, локальный или междугородний), который может быть выполнен различными пользователями или группами пользователей в организации. Подробные сведения [см.](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) в документации по планированию.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Просмотр записи использования PSTN с помощью панели управления Skype для бизнес-серверов

1. Откройте панель управления Skype для бизнес-серверов.

2. На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем щелкните **Использование ТСОП**.

3. На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.

    > [!NOTE]
    > На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Просмотр сведений об использовании PSTN с помощью команды Skype для управления бизнес-серверами

- Чтобы просмотреть сведения обо всех ваших приложениях PSTN, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:

  ```powershell
  Get-CsPstnUsage
  ```

    Эта команда возвращает следующую информацию:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>См. также

[Создание или изменение голосовой политики и настройка записей использования PSTN в Skype для бизнеса](voice-policy-and-pstn-usage-records.md)