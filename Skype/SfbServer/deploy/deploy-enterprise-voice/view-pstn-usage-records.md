---
title: Просмотр записей использования PSTN в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Сводка: сведения о том, как просматривать записи об использовании PSTN с помощью панели управления "Skype для бизнеса Server" или в командной консоли Skype для бизнеса Server.'
ms.openlocfilehash: d00fcab8c7f5ad9b8f47d5aecb6c6169e8d43574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300925"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Просмотр записей использования PSTN в Skype для бизнеса

**Сводка:** Сведения о том, как просматривать записи об использовании PSTN с помощью панели управления "Skype для бизнеса Server" или в командной консоли Skype для бизнеса Server.

В записи об использовании ТСОП указывается класс вызова (например, внутренний, локальный вызов или вызов на дальние расстояния), который может выполняться различными пользователями или группами пользователей в организации. Для получения дополнительных сведений см. [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) в документации по планированию.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Просмотр записи использования PSTN с помощью панели управления Skype для бизнеса Server

1. Откройте панель управления Skype для бизнеса Server.

2. На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем — **Использование ТСОП**.

3. На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.

    > [!NOTE]
    > На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Просмотр сведений об использовании PSTN с помощью командлетов командной консоли Skype для бизнеса Server

- Чтобы просмотреть сведения о всех используемых КТСОП, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.

  ```
  Get-CsPstnUsage
  ```

    Этой командой возвращается информация, аналогичная следующим сведениям:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>См. также

[Создание или изменение политики голосовой связи и настройка записей использования PSTN в Skype для бизнеса](voice-policy-and-pstn-usage-records.md)

