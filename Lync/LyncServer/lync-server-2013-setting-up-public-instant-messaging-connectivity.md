---
title: 'Lync Server 2013: Настройка подключения к общедоступным службам обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b3efe4e5d8e5cb84631969205842e56024394c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="27fdc-102">Настройка подключения к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27fdc-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27fdc-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="27fdc-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="27fdc-p101">Если ваша организация хочет поддерживает подключение к общедоступным системам обмена мгновенными сообщениями с AOL, нельзя использовать мастер развертывания Lync Server для запроса сертификата. Вместо этого выполните действия, описанные далее.</span><span class="sxs-lookup"><span data-stu-id="27fdc-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="27fdc-106">Настройка подключения к общедоступным системам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="27fdc-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="27fdc-p102">На интерфейсном сервере откройте построитель топологии. Разверните "Пограничные пулы", затем щелкните правой кнопкой мыши пограничный сервер или пул пограничных серверов. Выберите "Изменить свойства".</span><span class="sxs-lookup"><span data-stu-id="27fdc-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="27fdc-p103">В окне "Изменение свойств" в разделе "Общие" выберите "Включить федерацию для этого пограничного пула (порт 5061)". Нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="27fdc-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="27fdc-p104">Щелкните "Действие", выберите "Топология" и затем нажмите "Опубликовать". При появлении запроса о публикации топологии, нажмите кнопку "Далее". После завершения публикации нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="27fdc-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="27fdc-p105">На пограничном сервере откройте мастер развертывание Lync Server. Нажмите кнопку "Установить или обновить систему Lync Server", затем нажмите кнопку "Установить или удалить компоненты Lync Server". Затем снова нажмите "Выполнить".</span><span class="sxs-lookup"><span data-stu-id="27fdc-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="27fdc-p106">В диалоговом окне "Установка компонентов Lync Server" нажмите кнопку "Далее". В окне сводки будут показаны действия по мере их выполнения. После завершения развертывания нажмите кнопку "Просмотр журнала", чтобы открыть доступные файлы журналов. Нажмите кнопку "Готово", чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="27fdc-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="27fdc-122">Создание запроса на сертификат для внешнего интерфейса пограничного сервера для поддержки подключения к общедоступным системам обмена мгновенными сообщениями с AOL</span><span class="sxs-lookup"><span data-stu-id="27fdc-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="27fdc-123">Если необходимый шаблон доступен для CA, используйте следующий командлет Windows PowerShell на пограничном сервере для запроса сертификата</span><span class="sxs-lookup"><span data-stu-id="27fdc-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="27fdc-124">Имя сертификата по умолчанию для шаблона, используемого для Lync Server, — веб-сервер.</span><span class="sxs-lookup"><span data-stu-id="27fdc-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="27fdc-125">Указывайте имя \<\> шаблона только в том случае, если требуется использовать шаблон, отличный от шаблона по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27fdc-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="27fdc-126">Если в Организации требуется поддерживать связь с общедоступной службой обмена мгновенными сообщениями с AOL, необходимо использовать Windows PowerShell вместо мастера сертификатов, чтобы запросить сертификат для внешнего края службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="27fdc-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="27fdc-127">Это связано с тем, что шаблон веб-сервера центра сертификации (CA), используемый мастером сертификатов для запроса сертификата, не поддерживает клиентскую конфигурацию EKU.</span><span class="sxs-lookup"><span data-stu-id="27fdc-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="27fdc-128">Прежде чем использовать Windows PowerShell для создания сертификата, администратору ЦС необходимо создать и развернуть новый шаблон, поддерживающий клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="27fdc-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

