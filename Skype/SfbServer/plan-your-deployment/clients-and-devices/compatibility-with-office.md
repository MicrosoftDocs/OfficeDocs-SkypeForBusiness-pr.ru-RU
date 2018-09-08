---
title: Скайп для обеспечения совместимости бизнеса с помощью приложений Office
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Понимаете, могут получить доступ к Скайп для функции Business из Outlook и других приложений Microsoft Office.
ms.openlocfilehash: 8ab03b0da4bbc91080925bd15995f89ac0d3388f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886086"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Скайп для обеспечения совместимости бизнеса с помощью приложений Office
 
Понимаете, могут получить доступ к Скайп для функции Business из Outlook и других приложений Microsoft Office.
  
В этом разделе описываются совместимости Скайп для бизнеса с различными версиями Microsoft Office для настольных компьютеров. 
  
## <a name="office-and-skype-for-business"></a>Office и Скайп для бизнеса

В следующей таблице описываются Скайп для бизнеса функции, поддерживаемые различными версиями Office после развертывания и интеграции, как описано в [Интегрировать Скайп для Business Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)Exchange.
  
**Скайп для бизнеса и обеспечения совместимости Microsoft Office**

|**Функция**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 и 2016**|**2016 Office для Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Функции Outlook** ||||
|Настройка приглашений на собрания Outlook (добавление логотипа, URL-адреса справки, текста заявления об отказе, текста нижних колонтитулов)  |Нет  |Да   |Да|
|Настройка функции собрания, позволяющей по умолчанию выключать звук и видео участников    |Нет    |Да    |Нет    |
|Единое хранилище контактов для управления списков контактов по Office и Скайп для бизнеса    |Нет    |Да (требуется Exchange 2013 или более поздней версии)    |Да    |
|Фотографий высокого разрешения профиля    |Нет    |Да (требуется Exchange 2013 или более поздней версии)    |Да    |
|Состояние присутствия в Microsoft Outlook с него и поля «копия»    |Да    |Да    |Да    |
|Ответ с использованием мгновенных сообщений или вызов из меню «доступность»    |Да (из карточки контакта)    |Да (из карточки контакта)    |Да (из карточки контакта)    |
|Состояние присутствия в запросе на собрание на вкладке помощника по планированию    |Да    |Да    |Нет    |
|Ответить в мгновенном Сообщении или звонке из панели инструментов или ленты в полученной почте сообщение    |Да    |Да    |Да    |
|**Другие приложения Office**   ||||
|Общие заметки OneNote    |Нет    |Да    |Нет    |
|Настройка, интегрированная в программу настройки Office    |Нет    |Да    |Нет    |
|Содержимое презентации PowerPoint    |Да    |Да (VBSS также можно получить)    |Да    |
|Мгновенное сообщение и состояние присутствия в файлах Microsoft Word и Microsoft Excel (смарт-теги включены)    |Только Microsoft Word    |Только Microsoft Word    |Нет    |
|Мгновенные сообщения и состояния присутствия на сайтах Microsoft SharePoint (должно быть установлено приложение Outlook)    |Да    |Да    |Нет    |
   
& #x 2776; -Предполагается, что установлены и выполняются в настоящее время Скайп для бизнеса на клиенте Mac или Lync 2011 для Mac клиента.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server и Скайп для бизнеса

В следующей таблице описываются Скайп для бизнеса поддержка различных версий Exchange Server. Outlook необходимо установить на клиентском компьютере для обработки вызовов Extended MAPI, а для некоторых функций требуется использование служб Exchange Web Services (EWS).
  
**Скайп для бизнеса и совместимость с Exchange Server**

|**Версия сервера Exchange Server**|**Скайп для поддержки бизнеса**|
|:-----|:-----|
|Exchange Server 2019 (Скайп для Business Server 2019 только) |Аналогично поддержке Exchange Server 2013    |
|Exchange Server 2016    |Аналогично поддержке Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |То же, что поддержка Exchange Server 2010, с добавлением  <br/>&bull;&nbsp;&nbsp;Единое хранилище контактов  <br/>&bull;&nbsp;&nbsp;Фотографии с высоким разрешением  <br/>&bull;&nbsp;&nbsp;Архивация интеграции  <br/> **Примечание:** Дополнительные сведения см [Интегрировать Скайп для Business Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Скайп для Business Server 2015 только) |Следующие функции доступны только посредством служб EWS:  <br/>&bull;&nbsp;&nbsp;Чтение или удалять элементы в папке журнала бесед  <br/>&bull;&nbsp;&nbsp;Чтение или удалять элементы голосовой почты  <br/>&bull;&nbsp;&nbsp;Отобразить подробные сведения о доступности и тему и место собрания  <br/>&bull;&nbsp;&nbsp;Синхронизация контактов Exchange  <br/> Общедоступные папки — это дополнительный компонент в Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>См. также
 
[Требования к клиентскому Windows и поддержка программного обеспечения](windows-requirements.md)
  
[Планирование для клиентов собрания (веб-приложения и приложения собрания)](meetings-clients.md)

