---
title: Skype для бизнеса совместимость с Office приложениями
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Понимание способов доступа к Skype для бизнеса из Outlook и других Microsoft Office приложений.
ms.openlocfilehash: 249b66eb366d9fa2d5911c24fb7dc88d0dcd6633
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409902"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype для бизнеса совместимость с Office приложениями
 
Понимание способов доступа к Skype для бизнеса из Outlook и других Microsoft Office приложений.
  
В этом разделе описывается совместимость Skype для бизнеса различных версий Microsoft Office наборов. 
  
## <a name="office-and-skype-for-business"></a>Office и Skype для бизнеса

В следующей таблице описываются Skype для бизнеса, поддерживаемые различными версиями Office после развертывания Exchange и интеграции, как описано в статье [Skype для бизнеса Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype для бизнеса и Microsoft Office совместимости**

|**Функция**|**Microsoft Office 2010;**|**Microsoft Office 2013, 2015 и 2016**|**Office 2016 для Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook функции** ||||
|Настройка приглашений Outlook собраний (добавление логотипа, URL-адрес справки, отказ от ответственности, текст для подножки)  |Нет  |Да   |Да|
|Настройка параметра собрания, чтобы отключить аудио и видео участника по умолчанию    |Нет    |Да    |Нет    |
|Объединенный магазин контактов для управления списками контактов Office и Skype для бизнеса    |Нет    |Да (требуется Exchange 2013 или более поздней)    |Да    |
|Изображения профилей с высоким разрешением    |Нет    |Да (требуется Exchange 2013 или более поздней)    |Да    |
|Состояние присутствия в полях Microsoft Outlook From, To и Cc    |Да    |Да    |Да    |
|Ответ с помощью чата или вызова из меню доступности    |Да (с карточки контакта)    |Да (с карточки контакта)    |Да (с карточки контакта)    |
|Состояние присутствия в запросе на собрание на вкладке помощник по планированию    |Да    |Да    |Нет    |
|Ответ с помощью чата или вызова с панели инструментов или ленты в полученном сообщении электронной почты    |Да    |Да    |Да    |
|**Другие Office приложения**   ||||
|OneNote общие заметки    |Нет    |Да    |Нет    |
|Установка, интегрированная в Office программы установки    |Нет    |Да    |Нет    |
|PowerPoint презентации    |Да    |Да (также доступен VBSS)    |Да    |
|Чат и присутствие в Microsoft Word и Microsoft Excel файлах (включены смарт-теги)    |Microsoft Word только    |Microsoft Word только    |Нет    |
|Im и присутствие на сайтах SharePoint Майкрософт (Outlook должны быть установлены)    |Да    |Да    |Нет    |
   
&#x2776; предполагает, что вы установили и в настоящее время Skype для бизнеса на клиенте Mac или клиенте Lync 2011 для Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server и Skype для бизнеса

В следующей таблице Skype для бизнеса поддержка различных версий Exchange Server. Outlook должен быть установлен на клиентском компьютере для обработки расширенных вызовов MAPI, а некоторые функции требуют использования Exchange веб-служб (EWS).
  
**Skype для бизнеса и Exchange Server совместимости**

|**Exchange Server версии**|**Skype для бизнеса поддержки**|
|:-----|:-----|
|Exchange Server 2019 г. (только Skype для бизнеса Server 2019 г.) |То же, что Exchange Server 2013 г.    |
|Exchange Server 2016    |То же, что Exchange Server 2013 г.  <br/> |
|Exchange Server 2013  <br/> |То же, Exchange Server 2010 г., с добавлением  <br/>&bull;&nbsp;&nbsp;Объединенный магазин контактов  <br/>&bull;&nbsp;&nbsp;Изображения с высоким разрешением  <br/>&bull;&nbsp;&nbsp;Интеграция архивации  <br/> **Примечание:** Подробные сведения см. в [Skype для бизнеса Server Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(только Skype для бизнеса Server 2015 г.) |Следующие функции доступны только через EWS:  <br/>&bull;&nbsp;&nbsp;Чтение или удаление элементов в папке История бесед  <br/>&bull;&nbsp;&nbsp;Чтение или удаление элементов голосовой почты  <br/>&bull;&nbsp;&nbsp;Отображение расширенных бесплатных и загруженных сведений, темы собраний и расположения  <br/>&bull;&nbsp;&nbsp;Exchange синхронизации контактов  <br/> Общедоступные папки являются необязательными в Exchange Server 2010 г.  <br/> |
   
## <a name="see-also"></a>См. также
 
[Windows клиентских требований и поддержки программного обеспечения](windows-requirements.md)
  
[Планирование для клиентов собраний (Web App и Meetings App)](meetings-clients.md)

