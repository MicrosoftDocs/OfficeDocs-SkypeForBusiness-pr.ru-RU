---
title: Интеграция с Exchange и SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Сводка: Сведения о Скайп Business Server 2015 интеграции с Exchange и SharePoint.'
ms.openlocfilehash: 3031fa042a25895c7b398d88d1ff62b1b023b2e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919334"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Интеграция с Exchange и SharePoint

**Сводка:** Сведения о Скайп Business Server 2015 интеграции с Exchange и SharePoint.

Можно настроить Скайп для развертываний Business Server 2015 для интеграции с Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 и SharePoint Server, в локальной и online. Функции, приведенные в следующей таблице, поддерживаются всеми клиентами, если не указано иное. Дополнительные сведения о клиенте поддержки см [Сравнение функций для настольных компьютеров для Скайп для бизнеса](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) и Скайп для бизнеса в Интернет таблицы сравнения клиентов на [клиентах для Скайп для бизнеса в Интернет](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Интеграция с Exchange Server

В следующей таблице перечислены функции, поддерживаемые в гибридном развертывании при интеграции с Microsoft Exchange Server.

 **Скайп для Business Server локально и Exchange локально**


|**Функция**|**Примечания**|
|:-----|:-----|
|Обмен мгновенными сообщениями и присутствие в Outlook  <br/> |Для получения дополнительных сведений см [обмена мгновенными Сообщениями и присутствия](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> |Дополнительные сведения можно [Интегрировать Скайп для 2015 Business Server с Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Обмен мгновенными Сообщениями и сведений о присутствии в Outlook Web App  <br/> |Дополнительные сведения в статье [Configure гибридной среде Скайп для Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Расписание и присоединиться к собранию по сети через Outlook Web App  <br/> ||
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собраниям по сети в мобильных клиентах  <br/> |Для получения дополнительных сведений см [Развертывание мобильных устройств](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Список контактов (из единого хранилища контактов)  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Lync 2013 или Скайп для настольных компьютеров клиента Business является обязательным.  <br/>  Дополнительные сведения можно [Настроить Скайп для 2015 Business Server для использования в единое хранилище контактов](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Фотографии с высоким разрешением контакт в клиент Lync 2013, Скайп для клиента Business и Lync Web App.  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения содержатся в разделе [Настройка использования фотографий высокого разрешения в Скайп для Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Для фотографии на Скайп для бизнес-приложение для MAC и мобильные устройства интеграцию Скайп для Business Server 2015 и Exchange Server должны настраиваться как описано в [Настройка партнерских приложений в Скайп для Business Server и Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Для получения дополнительных сведений см [Скайп для гибридных решений для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Почтовый ящик exchange пользователя должны записываться пропущенных журнал бесед и журналы вызовов  <br/> ||
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Для получения дополнительных сведений см [Контрольный список развертывания для архивации](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Поиск заархивированного содержимого  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> |
|Голосовая почта  <br/> |Для получения дополнительных сведений см [Развертывание локального Exchange единой системы обмена СООБЩЕНИЯМИ для предоставления Lync Server 2013 голосовой почты](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Скайп для Business Server локально и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|Обмен мгновенными сообщениями и присутствие в Outlook  <br/> |Дополнительные сведения можно [настроить интеграцию локального Скайп Business Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> ||
|Обмен мгновенными Сообщениями и сведений о присутствии в Outlook Web App  <br/> |Дополнительные сведения можно [настроить интеграцию локального Скайп Business Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Расписание и присоединиться к собрания по сети из Outlook Web App  <br/> |Дополнительные сведения можно [настроить интеграцию локального Скайп Business Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собранию по сети в мобильных клиентах  <br/> ||
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Список контактов (из единого хранилища контактов).  <br/> |Lync Server только 2013. Lync 2013 или Скайп для настольных компьютеров клиента Business является обязательным.  <br/> Дополнительные сведения можно [Настроить Скайп для 2015 Business Server для использования в единое хранилище контактов](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Фотографии с высоким разрешением контакт в клиент Lync 2013, Скайп для клиента Business и Lync Web App.  <br/> |Дополнительные сведения содержатся в разделе [Настройка использования фотографий высокого разрешения в Скайп для Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Для фотографии на Скайп для бизнес-приложение для MAC и мобильные устройства интеграцию Скайп для Business Server 2015 и Exchange Server должны настраиваться как описано в [Настройка интеграции между локальной Скайп для Business Server и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Для получения дополнительных сведений см [Скайп для гибридных решений для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Почтовый ящик Exchange пользователя должны записываться пропущенных журнал бесед и журналы вызовов  <br/> ||
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> |Для получения дополнительных сведений см [Контрольный список развертывания для архивации](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Поиск заархивированного содержимого  <br/> |Дополнительные сведения см в [Настройка Exchange для центра обнаружения электронных данных SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Голосовая почта  <br/> |Дополнительные сведения содержатся в разделе [Предоставление Lync Server 2013 пользователям голосовой почты на Hosted Exchange единой системы обмена СООБЩЕНИЯМИ](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Скайп для бизнеса в Интернет и Exchange локально**


|**Функция**|**Примечания**|
|:-----|:-----|
|Присутствие в Outlook  <br/> ||
|Ответ с помощью мгновенного сообщения, вызова ТСОП, вызова Skype или видеовызова из сообщения электронной почты Outlook  <br/> ||
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> ||
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собраниям по сети в мобильных клиентах  <br/> ||
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Почтовый ящик exchange пользователя должны записываться пропущенных журнал бесед и журналы вызовов  <br/> ||
|Фотографии с высоким разрешением контакта в Lync 2013 или Скайп для клиента Business.  <br/> |Требуется Exchange 2016 или Exchange 2013. Это не поддерживается в Lync Web App, когда пользователи размещаются на Скайп для бизнеса в Интернет.  <br/> |
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Для получения дополнительных сведений см [Скайп для гибридных решений для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Почтовый ящик Exchange пользователя должны записываться пропущенных журнал бесед и журналы вызовов  <br/> ||
|Журнал бесед на стороне сервера  <br/> ||

 **Скайп для бизнеса в Интернете и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|Обмен мгновенными сообщениями и присутствие в Outlook  <br/> ||
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> ||
|Обмен мгновенными Сообщениями и сведений о присутствии в Outlook Web App  <br/> ||
|Расписание и присоединиться к собрания по сети из Outlook Web App  <br/> ||
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> ||
|Присоединение к собранию по сети в мобильных клиентах  <br/> ||
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> ||
|Почтовый ящик exchange пользователя должны записываться пропущенных журнал бесед и журналы вызовов  <br/> ||
|Список контактов (из единого хранилища контактов)  <br/> |Lync Server 2013 или Скайп для клиента Business требуется  <br/> |
|С высоким разрешением фотографии контакта в Lync 2013, Скайп для клиента Business и Lync Web App  <br/> ||
|Делегирование собрания  <br/> |Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально. Для получения дополнительных сведений см [Скайп для гибридных решений для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> ||
|Поиск заархивированного содержимого  <br/> ||
|Голосовая почта  <br/> ||

## <a name="integration-with-sharepoint"></a>Интеграция с SharePoint

В следующей таблице перечислены функции, поддерживаемые в гибридном развертывании при интеграции с SharePoint.

||**Локальная версия SharePoint**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Скайп для Business Server 2015 локальной** <br/> | Поиск по навыкам <br/>  Сведения о присутствии в SharePoint <br/> | Сведения о присутствии в SharePoint <br/> |
|**Skype для бизнеса Online** <br/> | Сведения о присутствии в SharePoint <br/> | Сведения о присутствии в SharePoint <br/> |


