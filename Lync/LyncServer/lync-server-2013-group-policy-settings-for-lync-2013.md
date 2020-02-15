---
title: 'Lync Server 2013: параметры групповой политики для Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba88fdce88280597e9e621c13267de2b9b76d0fb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="50ace-102">Параметры групповой политики для Lync 2013</span><span class="sxs-lookup"><span data-stu-id="50ace-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50ace-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="50ace-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="50ace-104">В предыдущих версиях Lync и Office Communicator был доступен автономный административный шаблон Communicator. adm для настройки параметров групповой политики клиентов.</span><span class="sxs-lookup"><span data-stu-id="50ace-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="50ace-105">Для Lync 2013 новые файлы административных шаблонов (ADMX-и ADML-файлы) включены вместе с административным шаблоном групповой политики Office.</span><span class="sxs-lookup"><span data-stu-id="50ace-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="50ace-106">Доступность файлов Lync 2013. ADMX и ADML позволяет загружать шаблоны и централизованно управлять параметрами групповой политики для всех приложений Office и языковых пакетов.</span><span class="sxs-lookup"><span data-stu-id="50ace-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="50ace-107">Дополнительные сведения: "файлы административных шаблонов Office 2013 (ADMX, ADML)" в документации по Office 2013 по адресу <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span><span class="sxs-lookup"><span data-stu-id="50ace-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="50ace-108">Политики начальной загрузки клиентов</span><span class="sxs-lookup"><span data-stu-id="50ace-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="50ace-109">Существует ряд политик начальной загрузки клиентов которые следует настроить до того, как пользователи смогут первый раз выполнить вход на сервер.</span><span class="sxs-lookup"><span data-stu-id="50ace-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="50ace-110">Так как эти политики вступают в силу до того, как клиент войдет в систему и начнет получать с сервера параметры подготовки, их можно определять с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="50ace-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="50ace-111">Дополнительные сведения приведены в статье [Настройка политик начальной загрузки клиентов в Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="50ace-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

