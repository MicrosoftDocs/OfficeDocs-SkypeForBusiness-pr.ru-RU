---
title: Интеграция с Exchange и SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Сводка: сведения о интеграции Skype для бизнеса Server 2015 с Exchange и SharePoint.'
ms.openlocfilehash: 9d5f665d5bffede2de10c77735ea76fe55337af8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799809"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Интеграция с Exchange и SharePoint

**Сводка:** Узнайте больше о интеграции Skype для бизнеса Server 2015 с Exchange и SharePoint.

Вы можете настроить развертывание Skype для бизнеса Server 2015 для интеграции с Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 и SharePoint Server, как локально, так и в сети. Функции, приведенные в следующей таблице, поддерживаются всеми клиентами, если не указано иное. Дополнительные сведения о поддержке клиентов можно найти в разделе [Сравнение функций клиента для настольных компьютеров Skype для бизнеса](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) и Skype для бизнеса Online на клиентах [Skype для бизнеса Online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Интеграция с Exchange Server

В таблице ниже перечислены функции, которые поддерживаются в гибридном развертывании при интеграции с Microsoft Exchange Server.

 **Skype для бизнеса Server локально и Exchange в локальной среде**


|**Функция**|**Примечания**|
|:-----|:-----|
|Обмен мгновенными сообщениями и присутствие в Outlook  <br/> |Дополнительные сведения можно найти в разделе [Обмен сообщениями и сведения о присутствии](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> |Дополнительные сведения можно найти в разделе [интеграция Skype для бизнеса Server 2015 с сервером Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Обмен мгновенными сообщениями и присутствие в Outlook Web App  <br/> |Дополнительные сведения можно найти [в разделе Настройка гибридной среды в Skype для бизнеса Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Планирование и присоединение к собранию по сети с помощью Outlook Web App  <br/> ||
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собраниям по сети в мобильных клиентах  <br/> |Дополнительные сведения можно найти в разделе [развертывание мобильных устройств](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Список контактов (из единого хранилища контактов)  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Требуется клиент Lync 2013 или Skype для бизнеса для настольных компьютеров.  <br/>  Дополнительные сведения можно найти в разделе [Настройка Skype для бизнеса Server 2015 для работы с единым хранилищем контактов](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Фотография контакта с высоким разрешением в клиенте Lync 2013, клиенте Skype для бизнеса и Lync Web App.  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения можно найти [в статье Настройка использования фотографий высокого разрешения в Skype для бизнеса Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Для фотографий в приложении Skype для бизнеса для MAC и мобильных устройств интеграция между Skype для бизнеса Server 2015 и Exchange Server должна быть настроена так, как описано в разделе [Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Дополнительные сведения можно найти в разделе [гибридные решения Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Журнал посещенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя.  <br/> ||
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения можно найти в разделе [Контрольный список развертывания для архивации](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Поиск заархивированного содержимого  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> |
|Голосовая почта  <br/> |Дополнительные сведения можно найти в разделе [развертывание локальной системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype для бизнеса Server локально и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|Обмен мгновенными сообщениями и присутствие в Outlook  <br/> |Дополнительные сведения можно найти [в разделе Настройка интеграции между локальной системой Skype для бизнеса Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> ||
|Обмен мгновенными сообщениями и присутствие в Outlook Web App  <br/> |Дополнительные сведения можно найти [в разделе Настройка интеграции между локальной системой Skype для бизнеса Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Планирование и присоединение к собранию по сети из Outlook Web App  <br/> |Дополнительные сведения можно найти [в разделе Настройка интеграции между локальной системой Skype для бизнеса Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собранию по сети в мобильных клиентах  <br/> ||
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Список контактов (из единого хранилища контактов).  <br/> |Только для Lync Server 2013. Требуется клиент Lync 2013 или Skype для бизнеса для настольных компьютеров.  <br/> Дополнительные сведения можно найти в разделе [Настройка Skype для бизнеса Server 2015 для работы с единым хранилищем контактов](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) . <br/> |
|Фотография контакта с высоким разрешением в клиенте Lync 2013, клиенте Skype для бизнеса и Lync Web App.  <br/> |Дополнительные сведения можно найти [в статье Настройка использования фотографий высокого разрешения в Skype для бизнеса Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Для фотографий в приложении Skype для бизнеса на MAC и мобильном устройстве интеграция между Skype для бизнеса Server 2015 и Exchange Server должна быть настроена так, как описано в разделе [Настройка интеграции между локальными приложениями Skype для бизнеса Server и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Дополнительные сведения можно найти в разделе [гибридные решения Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Журнал посещенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя.  <br/> ||
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> |Дополнительные сведения можно найти в разделе [Контрольный список развертывания для архивации](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Поиск заархивированного содержимого  <br/> |Дополнительные сведения можно найти в разделе [Настройка Exchange для центра обнаружения электронных данных в SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Голосовая почта  <br/> |Дополнительные сведения можно найти [в разделе Предоставление пользователям Lync Server 2013 голосовой почты в размещенной UM единой системе обмена сообщениями](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype для бизнеса Online и Exchange в локальной среде**


|**Функция**|**Примечания**|
|:-----|:-----|
|Присутствие в Outlook  <br/> ||
|Ответ с помощью мгновенного сообщения, вызова ТСОП, вызова Skype или видеовызова из сообщения электронной почты Outlook  <br/> ||
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> ||
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собраниям по сети в мобильных клиентах  <br/> ||
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Журнал посещенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя.  <br/> ||
|Фотография контакта с высоким разрешением в Lync 2013 или клиенте Skype для бизнеса.  <br/> |Требуется Exchange 2016 или Exchange 2013. Это не поддерживается в Lync Web App, если пользователи находятся в Skype для бизнеса Online.  <br/> |
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Дополнительные сведения можно найти в разделе [гибридные решения Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Журнал посещенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя.  <br/> ||
|Журнал бесед на стороне сервера  <br/> ||

 **Skype для бизнеса Online и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|Обмен мгновенными сообщениями и присутствие в Outlook  <br/> ||
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> ||
|Обмен мгновенными сообщениями и присутствие в Outlook Web App  <br/> ||
|Планирование и присоединение к собранию по сети из Outlook Web App  <br/> ||
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собранию по сети в мобильных клиентах  <br/> ||
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Журнал посещенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя.  <br/> ||
|Список контактов (из единого хранилища контактов)  <br/> |Требуется клиент Lync Server 2013 или Skype для бизнеса  <br/> |
|Фотография контакта с высоким разрешением в Lync 2013, клиенте Skype для бизнеса и Lync Web App  <br/> ||
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Дополнительные сведения можно найти в разделе [гибридные решения Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> ||
|Поиск заархивированного содержимого  <br/> ||
|Голосовая почта  <br/> ||

## <a name="integration-with-sharepoint"></a>Интеграция с SharePoint

В таблице ниже перечислены функции, которые поддерживаются в гибридном развертывании при интеграции с SharePoint.

||**Локальная среда SharePoint**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype для бизнеса Server 2015 в локальной среде** <br/> | Поиск по навыкам <br/>  Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |
|**Skype для бизнеса Online** <br/> | Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |


