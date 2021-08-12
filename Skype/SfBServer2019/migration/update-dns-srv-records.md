---
title: Обновление записей DNS SRV
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
ms.openlocfilehash: 0c3454bd4fbf8ecdc28730da378357e9d50efec3c12ba5b3926abb61010979ab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327055"
---
# <a name="update-dns-srv-records"></a>Обновление записей DNS SRV

Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
  
В этом разделе описывается обновление записей системы доменных имен (DNS) после переноса на Skype для бизнеса Server 2019 г. После того как все пользователи были перемещены в Skype для бизнеса Server 2019 г., но до вывода из эксплуатации устаревшего пула или директора необходимо обновить записи SRV DNS во внутреннем DNS для каждого домена SIP. В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Настройка DNS-записи SRV

1. На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.
    
2. В дереве консоли для домена SIP раздвигайте зоны forward **lookup,** раздвигайте домен SIP, в котором установлен Skype для бизнеса Server 2019 г., и перейдите **к** _tcp параметру. 
    
3. В правой области щелкните правой кнопкой **мыши** _sipinternaltls выберите **свойства**.
    
4. В **хост,предлагающих** эту службу, обновим хост-FQDN, чтобы указать на Skype для бизнеса Server 2019 г.
    
5. Нажмите кнопку **ОК**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Проверка возможности разрешения полного доменного имени интерфейсного пула или сервера Standard Edition

1. Войдите на клиентский компьютер в домене.
    
2. Нажмите кнопку **Пуск** и выберите команду **Выполнить**.
    
3. В поле **Открыть** введите cmd и нажмите кнопку **ОК**.
    
4. В командной подсказке введите nslookup _\<FQDN of the Front End pool\>_ или , а затем нажмите  _\<FQDN of the Standard Edition server\>_ ВВОД.
    
5. Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.
    

