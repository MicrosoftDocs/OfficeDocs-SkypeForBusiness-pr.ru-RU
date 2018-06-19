---
title: Скайп для обеспечения совместимости бизнеса с помощью приложений Office
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Понимаете, могут получить доступ к Скайп для функции Business из Outlook и других приложений Microsoft Office.
ms.openlocfilehash: 49bfb52925855ad7fd5ce0564056cfd8c5039ef6
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503986"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Скайп для обеспечения совместимости бизнеса с помощью приложений Office
 
Понимаете, могут получить доступ к Скайп для функции Business из Outlook и других приложений Microsoft Office.
  
В этом разделе описываются совместимости Скайп для бизнеса с различными версиями Microsoft Office для настольных компьютеров. 
  
## <a name="office-and-skype-for-business"></a>Office и Скайп для бизнеса

В следующей таблице описываются Скайп для бизнеса функции, поддерживаемые различными версиями Office после развертывания и интеграции, как описано в [Интегрировать Скайп для 2015 Business Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)Exchange.
  
**Скайп для бизнеса и обеспечения совместимости Microsoft Office**

|**Функция**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 и 2016**|**2016 Office для Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Функции Outlook** <br/> ||||
|Настройка приглашений на собрания Outlook (добавление логотипа, URL-адреса справки, текста заявления об отказе, текста нижних колонтитулов)  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Настройка функции собрания, позволяющей по умолчанию выключать звук и видео участников  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Единое хранилище контактов для управления списков контактов по Office и Скайп для бизнеса  <br/> |Нет  <br/> |Да (требуется Exchange 2013 или более поздней версии)  <br/> |Да  <br/> |
|Фотографий высокого разрешения профиля  <br/> |Нет  <br/> |Да (требуется Exchange 2013 или более поздней версии)  <br/> |Да  <br/> |
|Состояние присутствия в Microsoft Outlook с него и поля «копия»  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Ответ с использованием мгновенных сообщений или вызов из меню «доступность»  <br/> |Да (из карточки контакта)  <br/> |Да (из карточки контакта)  <br/> |Да (из карточки контакта)  <br/> |
|Состояние присутствия в запросе на собрание на вкладке помощника по планированию  <br/> |Да  <br/> |Да  <br/> |Нет  <br/> |
|Ответить в мгновенном Сообщении или звонке из панели инструментов или ленты в полученной почте сообщение  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|**Другие приложения Office** <br/> ||||
|Общие заметки OneNote  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Настройка, интегрированная в программу настройки Office  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Содержимое презентации PowerPoint  <br/> |Да  <br/> |Да  <br/> (Также доступен VBSS)  <br/> |Да  <br/> |
|Мгновенное сообщение и состояние присутствия в файлах Microsoft Word и Microsoft Excel (смарт-теги включены)  <br/> |Только Microsoft Word  <br/> |Только Microsoft Word  <br/> |Нет  <br/> |
|Мгновенные сообщения и состояния присутствия на сайтах Microsoft SharePoint (должно быть установлено приложение Outlook)  <br/> |Да  <br/> |Да  <br/> |Нет  <br/> |
   
& #x 2776; -Предполагается, что установлены и выполняются в настоящее время Скайп для бизнеса на клиенте Mac или Lync 2011 для Mac клиента.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server и Скайп для бизнеса

В следующей таблице описываются Скайп для бизнеса поддержка различных версий Exchange Server. Outlook необходимо установить на клиентском компьютере для обработки вызовов Extended MAPI, а для некоторых функций требуется использование служб Exchange Web Services (EWS).
  
**Скайп для бизнеса и совместимость с Exchange Server**

|**Версия Exchange Server**|**Скайп для поддержки бизнеса**|
|:-----|:-----|
|Exchange Server 2016  <br/> |Аналогично поддержке Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |То же, что поддержка Exchange Server 2010, с добавлением  <br/>&bull;&nbsp;&nbsp;Единое хранилище контактов  <br/>&bull;&nbsp;&nbsp;Фотографии с высоким разрешением  <br/>&bull;&nbsp;&nbsp;Архивация интеграции  <br/> **Примечание:** Дополнительные сведения см [Интегрировать Скайп для 2015 Business Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/> |Следующие функции доступны только посредством служб EWS:  <br/>&bull;&nbsp;&nbsp;Чтение или удалять элементы в папке журнала бесед  <br/>&bull;&nbsp;&nbsp;Чтение или удалять элементы голосовой почты  <br/>&bull;&nbsp;&nbsp;Отобразить подробные сведения о доступности и тему и место собрания  <br/>&bull;&nbsp;&nbsp;Синхронизация контактов Exchange  <br/> Общедоступные папки — это дополнительный компонент в Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>См. также
 
[Требования к клиентскому Windows и поддержка программного обеспечения](windows-requirements.md)
  
[Планирование для клиентов собрания (веб-приложения и приложения собрания)](meetings-clients.md)

[Взаимодействие с клиентом в Lync 2013](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[Требования к клиентской системе](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Требования к приложение Lync магазина Windows](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)