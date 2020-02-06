---
title: Совместимость Skype для бизнеса с приложениями Office
ms.author: v-lanac
author: lanachin
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
description: Узнайте о том, как получить доступ к функциям Skype для бизнеса из Outlook и других приложений Microsoft Office.
ms.openlocfilehash: e91174850cb82d325eb9a3f75577d3aaeb3b90f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803689"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Совместимость Skype для бизнеса с приложениями Office
 
Узнайте о том, как получить доступ к функциям Skype для бизнеса из Outlook и других приложений Microsoft Office.
  
В этой статье описаны вопросы совместимости Skype для бизнеса с различными версиями наборов Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office и Skype для бизнеса

В таблице ниже описаны функции Skype для бизнеса, которые поддерживаются различными версиями Office после развертывания и интеграции Exchange, как описано в статье [интеграция Skype для бизнеса Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Совместимость с Skype для бизнеса и Microsoft Office**

|**Функция**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 и 2016**|&#x2776; **Office 2016 для Mac** |
|:-----|:-----|:-----|:-----|
|**Функции Outlook** ||||
|Настройка приглашений на собрания Outlook (добавление логотипа, URL-адреса справки, текста заявления об отказе, текста нижних колонтитулов)  |Нет  |Да   |Да|
|Настройка функции собрания, позволяющей по умолчанию выключать звук и видео участников    |Нет    |Да    |Нет    |
|Единое хранилище контактов для управления списками контактов в Office и Skype для бизнеса    |Нет    |Да (требуется Exchange 2013 или более поздней версии)    |Да    |
|Фотографии профилей с высоким разрешением    |Нет    |Да (требуется Exchange 2013 или более поздней версии)    |Да    |
|Состояние присутствия в полях "от", "Кому" и "копия" в Microsoft Outlook    |Да     |Да     |Да     |
|Ответ с помощью мгновенного сообщения или звонка из меню доступности    |Да (из карточки контакта)    |Да (из карточки контакта)    |Да (из карточки контакта)    |
|Состояние присутствия в запросе на собрание на вкладке помощника по планированию    |Да     |Да    |Нет    |
|Ответ с помощью МГНОВЕННОго сообщения или звонка с панели инструментов или ленты в полученном сообщении электронной почты    |Да     |Да     |Да     |
|**Другие приложения Office**   ||||
|Общие заметки OneNote    |Нет    |Да    |Нет    |
|Настройка, интегрированная в программу настройки Office    |Нет    |Да    |Нет    |
|Содержимое презентации PowerPoint    |Да    |Да (VBSS также доступен)    |Да    |
|Мгновенное сообщение и состояние присутствия в файлах Microsoft Word и Microsoft Excel (смарт-теги включены)    |Только Microsoft Word    |Только Microsoft Word    |Нет    |
|Мгновенные сообщения и состояния присутствия на сайтах Microsoft SharePoint (должно быть установлено приложение Outlook)    |Да    |Да    |Нет    |
   
&#x2776;-предполагается, что вы установили клиент Skype для бизнеса для Mac или Lync 2011 для Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server и Skype для бизнеса

В следующей таблице описано, как поддерживать Skype для бизнеса для разных версий Exchange Server. Outlook необходимо установить на клиентском компьютере для обработки вызовов Extended MAPI, а для некоторых функций требуется использование служб Exchange Web Services (EWS).
  
**Совместимость с Skype для бизнеса и Exchange Server**

|**Версия сервера Exchange Server**|**Поддержка Skype для бизнеса**|
|:-----|:-----|
|Exchange Server 2019 (только для Skype для бизнеса Server 2019) |Аналогично поддержке Exchange Server 2013    |
|Exchange Server 2016    |Аналогично поддержке Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |То же, что и служба поддержки Exchange Server 2010, с добавлением  <br/>&bull;&nbsp;&nbsp;Единое хранилище контактов  <br/>&bull;&nbsp;&nbsp;Рисунки с высоким разрешением  <br/>&bull;&nbsp;&nbsp;Интеграция архивации  <br/> **Примечание.** Подробности можно найти [в разделе Интеграция Skype для бизнеса Server с сервером Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Только для Skype для бизнеса Server 2015) |Следующие функции доступны только посредством служб EWS:  <br/>&bull;&nbsp;&nbsp;Чтение и удаление элементов в папке "Журнал бесед"  <br/>&bull;&nbsp;&nbsp;Чтение и удаление элементов голосовой почты  <br/>&bull;&nbsp;&nbsp;Отображение дополнительных сведений о доступности, а затем темы и местоположения собрания  <br/>&bull;&nbsp;&nbsp;Синхронизация контактов Exchange  <br/> Общедоступные папки — это дополнительный компонент в Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>См. также
 
[Требования к клиенту для Windows и поддержка программного обеспечения](windows-requirements.md)
  
[Планирование для клиентов собраний (Skype для бизнеса Web App и приложение "Собрания Skype")](meetings-clients.md)

