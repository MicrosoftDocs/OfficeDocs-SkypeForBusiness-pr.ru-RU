---
title: Просмотр записей об использовании ЗВОНКОВ в Skype для бизнеса
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
description: Сводка. Узнайте, как просматривать записи об использовании PSTN с помощью панели управления Skype для бизнеса Server или в оболочке управления Skype для бизнеса Server.
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830539"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Просмотр записей об использовании ЗВОНКОВ в Skype для бизнеса

**Сводка:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.

В записи об использовании телефонной сети общего пользования (PSTN) указывается класс звонка (например, внутренний, локальный или междугородный), который может быть выполнен различными пользователями или группами пользователей в организации. Подробные сведения [см.](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) в документации по планированию.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Просмотр записи использования PSTN с помощью панели управления Skype для бизнеса Server

1. Откройте панель управления Skype для бизнеса Server.

2. На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем щелкните **Использование ТСОП**.

3. На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.

    > [!NOTE]
    > На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Просмотр сведений об использовании PSTN с помощью команды Skype для бизнеса Server Management Shell

- Чтобы просмотреть сведения обо всех типах использования PSTN, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:

  ```powershell
  Get-CsPstnUsage
  ```

    Эта команда возвращает следующую информацию:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>См. также

[Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)

