---
title: 'Lync Server 2013: использование командлетов для отмены подготовки домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c280cdcaa9d06b9ce7eee02cb043ecba0a9deb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="2f8ae-102">Использование командлетов для обратной подготовки домена для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f8ae-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f8ae-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="2f8ae-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="2f8ae-104">Использование командлета  **Disable-CsAdDomain** для отмены этапа подготовки домена.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="2f8ae-105">Использование командлетов для отмены подготовки домена</span><span class="sxs-lookup"><span data-stu-id="2f8ae-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="2f8ae-106">Войдите на любой сервер в домене как член группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="2f8ae-107">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2f8ae-108">Выполняем</span><span class="sxs-lookup"><span data-stu-id="2f8ae-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="2f8ae-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="2f8ae-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="2f8ae-110">Если параметр Force присутствует, выполняется откат для подготовки домена, даже если активируются один или несколько серверов переднего плана или серверов аудио-и видеоконференций в домене.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="2f8ae-111">Если параметр Force отсутствует, откат подготовки домена завершается, если активированы какие-либо серверы переднего плана или серверы конференций аудио-и видеоконференций в домене.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f8ae-112">Параметр GlobalSettingsDomainController позволяет указать, где хранятся глобальные настройки.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="2f8ae-113">Если ваши параметры хранятся в системном контейнере (что типично для обновленных развертываний, в которых глобальный параметр не был перенесен в контейнер конфигурации), определите контроллер домена в корне леса Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="2f8ae-114">Если глобальные параметры размещены в контейнере конфигурации (что типично для новых или обновленных развертываний, в которых глобальный параметр был перенесен в контейнер конфигурации), определите любой контроллер домена в лесу.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="2f8ae-115">Если не указать этот параметр, командлет предполагает, что параметры хранятся в контейнере конфигурации и ссылаются на любой контроллер домена в доменных службах Active&nbsp;Directory.</span><span class="sxs-lookup"><span data-stu-id="2f8ae-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f8ae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2f8ae-116">See Also</span></span>


[<span data-ttu-id="2f8ae-117">Выполнение подготовки домена для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f8ae-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="2f8ae-118">Подготовка доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f8ae-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

