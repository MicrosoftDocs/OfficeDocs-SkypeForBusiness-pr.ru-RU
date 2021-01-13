---
title: Совместимость Skype для бизнеса с приложениями Office
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: В этой теме представлены способы доступа к функциям Skype для бизнеса из Outlook и других Microsoft Office приложений.
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802739"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Совместимость Skype для бизнеса с приложениями Office
 
В этой теме представлены способы доступа к функциям Skype для бизнеса из Outlook и других Microsoft Office приложений.
  
В этом разделе описывается совместимость Skype для бизнеса с различными версиями Microsoft Office наборов. 
  
## <a name="office-and-skype-for-business"></a>Office и Skype для бизнеса

В следующей таблице описаны функции Skype для бизнеса, которые поддерживаются различными версиями Office после развертывания и интеграции Exchange, как описано в статье "Интеграция Skype для бизнеса [Server с](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)Exchange Server.
  
**Совместимость Skype для бизнеса и Microsoft Office**

|**Функция**|**Microsoft Office 2010;**|**Microsoft Office 2013, 2015 и 2016**|**Office 2016 для Mac &#x2776;** |
|:-----|:-----|:-----|:-----|
|**Функции Outlook** ||||
|Настройка приглашений на собрания Outlook (добавление логотипа, URL-адреса справки, заявления об отказе, текста для footer)  |Нет  |Да   |Да|
|Настройка параметра собрания для звука и видео участников по умолчанию    |Нет    |Да    |Нет    |
|Единое хранилище контактов для управления списками контактов в Office и Skype для бизнеса    |Нет    |Да (требуется Exchange 2013 или более поздней)    |Да    |
|Изображения профиля с высоким разрешением    |Нет    |Да (требуется Exchange 2013 или более поздней)    |Да    |
|Состояние присутствия в полях Microsoft Outlook From, To и Cc    |Да    |Да    |Да    |
|Ответ с помощью мгновенных данных или звонка из меню доступности    |Да (из карточки контакта)    |Да (из карточки контакта)    |Да (из карточки контакта)    |
|Состояние присутствия в запросе на собрание на вкладке помощник по планированию    |Да    |Да    |Нет    |
|Ответ с помощью мгновенных сообщений или звонка с панели инструментов или ленты в полученном сообщении электронной почты    |Да    |Да    |Да    |
|**Другие приложения Office**   ||||
|Общие заметки OneNote    |Нет    |Да    |Нет    |
|Программа установки, интегрированная в программу установки Office    |Нет    |Да    |Нет    |
|Содержимое презентации PowerPoint    |Да    |Да (также доступна VBSS)    |Да    |
|Мгновенные данные и присутствие в файлах Microsoft Word и Microsoft Excel (смарт-теги включены)    |Только Microsoft Word    |Только Microsoft Word    |Нет    |
|Im and presence in Microsoft SharePoint sites (Outlook must be installed)    |Да    |Да    |Нет    |
   
&#x2776; предполагает, что вы установили и в настоящее время работаете с клиентом Skype для бизнеса на Mac или клиентом Lync 2011 для Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server и Skype для бизнеса

В следующей таблице описывается поддержка Skype для бизнеса для различных версий Exchange Server. Outlook необходимо установить на клиентском компьютере для обработки расширенных вызовов MAPI, а для некоторых функций требуется использование веб-служб Exchange (EWS).
  
**Совместимость Skype для бизнеса и Exchange Server**

|**Exchange Server версии**|**Поддержка Skype для бизнеса**|
|:-----|:-----|
|Exchange Server 2019 (только Skype для бизнеса Server 2019) |То же, Exchange Server 2013    |
|Exchange Server 2016    |То же, что Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |То же, Exchange Server 2010, с добавлением  <br/>&bull;&nbsp;&nbsp;Единое хранилище контактов  <br/>&bull;&nbsp;&nbsp;Изображения с высоким разрешением  <br/>&bull;&nbsp;&nbsp;Интеграция архивации  <br/> **Примечание.** For details, see [Integrate Skype for Business Server with Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Exchange Server 2010  <br/>(Только Skype для бизнеса Server 2015) |Следующие функции доступны только через EWS:  <br/>&bull;&nbsp;&nbsp;Чтение и удаление элементов в папке "История бесед"  <br/>&bull;&nbsp;&nbsp;Чтение и удаление элементов голосовой почты  <br/>&bull;&nbsp;&nbsp;Отображение расширенных сведений о занятости, теме и расположении собрания  <br/>&bull;&nbsp;&nbsp;Синхронизация контактов Exchange  <br/> Общедоступные папки являются необязательными в Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>См. также
 
[Требования к клиенту Windows и поддержка программного обеспечения](windows-requirements.md)
  
[Планирование клиентов собраний (Веб-приложение и приложение для собраний)](meetings-clients.md)

