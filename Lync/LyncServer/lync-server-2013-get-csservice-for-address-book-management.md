---
title: 'Lync Server 2013: Get-Кссервице для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cfa9bd42bb29ca32ab27dc64d2ee9a111abab8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>Get-Кссервице для управления адресными книгами в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Кто может запустить этот командлет: по умолчанию членам следующих групп разрешено выполнять командлет Get-Кссервице локально: Рткуниверсалусерадминс, Рткуниверсалсерверадминс. Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-Кссервице является ценным для получения и отображения текущей конфигурации определенных веб-служб инфраструктуры. Определив полное доменное имя (FQDN) для пула и веб-сервер параметров, командлет выводит на экран службы, предоставляемые вашим сервером, в том числе URI обработчика адресной книги и расширения списка рассылки.

Например:

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

Этот командлет возвращает следующее:

Identity::pool01. contoso. NET

Хранилище файлов: хранилища файлов:DC01. contoso. NET

Усерсервер: Усерсервер:pool01. contoso. NET

Примарихттппорт: 80

Примарихттпспорт: 443

Екстерналхттппорт: 8080

Екстерналхттпспорт: 4443

Публишедпримарихттппорт: 80

Публишедпримарихттпспорт: 443

Публишедекстерналхттппорт: 80

Публишедекстерналхттпспорт: 443

Реачпримарипсомсерверпорт: 8060

Реачекстерналпсомсерверпорт: 8061

Аппшарингпортстарт: 49152

Аппшарингпорткаунт: 16383

Лисервицеинтерналури:https://internalweb.contoso.net/locationinformation/liservice.svc

Абхандлеринтерналури:https://internalweb.contoso.net/abs/handler

Абхандлерекстерналури:https://csweb.contoso.com/abs/handler

Длекспансионинтерналури:https://internalweb.contoso.net/groupexpansion/service.svc

Длекспансионекстерналури:https://csweb.contoso.com/groupexpansion/service.svc

Кахандлеринтерналури:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

Кахандлеринтерналанонури:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

Коллабконтентинтерналури:https://internalweb.contoso.net/CollabContent

Коллабконтентекстерналури:https://csweb.contoso.com/CollabContent

Кахандлерекстерналури:https://csweb.contoso.com/CertProv/CertProvisioningService.svc

Девицеупдатедовнлоадинтерналури:https://internalweb.contoso.net/RequestHandler/ucdevice.upx

Девицеупдатедовнлоадекстерналури:https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

Девицеупдатестореинтерналури:http://internalweb.contoso.net/RequestHandler/Files

Девицеупдатесторикстерналури:https://csweb.contoso.com/RequestHandlerExt/Files

Ргсажентсервицеинтерналури:https://internalweb.contoso.net/RgsClients/AgentService.svc

Ргсажентсервицеекстерналури:https://csweb.contoso.com/RgsClients/AgentService.svc

Митекстерналури:https://csweb.contoso.com/Meet

Диалинекстерналури:https://csweb.contoso.com/Dialin

Кскпинтерналури:https://internalweb.contoso.net/Cscp

Реачекстерналури:https://csweb.contoso.com/Reach

Реачинтерналури:https://internalweb.contoso.net/Reach

Вебтиккетекстерналури:https://csweb.contoso.com/WebTicket/WebTicketService.svc

Вебтиккетинтерналури:https://internalweb.contoso.net/WebTicket/WebTicketService.svc

Екстерналфкдн: csweb.contoso.com

Интерналфкдн: internalweb.contoso.net

Депендентсервицелист: {регистратор:pool01. contoso. NET, КонференЦингсервер:pool01. contoso. NET}

Сервицеид: 1 — WebService-1

Идентификатор сайта: сайт Redmond

Пулфкдн: pool01.contoso.net

Версия: 5

Роль: сервер

<div>

## <a name="see-also"></a>См. также


[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

