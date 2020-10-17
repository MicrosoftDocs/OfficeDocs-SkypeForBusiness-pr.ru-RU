---
title: Планирование Федерации Extensible Messaging and Presence Protocol (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4308bd09d571c41349ed9362affa220cf9723e3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526536"
---
# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="37f19-102">Планирование Федерации XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37f19-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37f19-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="37f19-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="37f19-104">Предыдущие версии Lync Server и Office Communications Server предоставили шлюз XMPP (Extensible Messaging and Presence Protocol), который может быть развернут как отдельная роль сервера, чтобы разрешить федерацию с развертываниями XMPP.</span><span class="sxs-lookup"><span data-stu-id="37f19-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="37f19-105">В Microsoft Lync Server 2013 функция XMPP может быть развернута в качестве компонента.</span><span class="sxs-lookup"><span data-stu-id="37f19-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="37f19-106">Функции XMPP устанавливаются в двух частях: прокси-сервер XMPP, выполняющийся на пограничном сервере, и шлюз XMPP, работающий на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="37f19-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="37f19-107">Развертывание и Настройка XMPP рассматривается в разделе [развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) вы планируете поддерживать XMPP в Организации, определяя правила портов и протоколов в брандмауэре, настройку сертификатов и добавление записей DNS.</span><span class="sxs-lookup"><span data-stu-id="37f19-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="37f19-108">В следующих подразделах этого раздела приводится сводка сведений, необходимых для успешного планирования Федерации XMPP для развертывания.</span><span class="sxs-lookup"><span data-stu-id="37f19-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="37f19-109">Функция XMPP Lync Server 2013 тестируется и поддерживается корпорацией Майкрософт для федерации обмена мгновенными сообщениями с Google говорите.</span><span class="sxs-lookup"><span data-stu-id="37f19-109">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="37f19-110">Для любой другой системы XMPP обратитесь к сторонним поставщикам, чтобы убедиться, что они поддерживают Федерацию с Lync Server 2013, а также рекомендации по развертыванию и устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="37f19-110">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37f19-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="37f19-111">In This Section</span></span>

  - [<span data-ttu-id="37f19-112">Сводка по сертификатам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37f19-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="37f19-113">Сводка по портам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37f19-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="37f19-114">Сводка по DNS — Федерация XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37f19-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37f19-115">См. также</span><span class="sxs-lookup"><span data-stu-id="37f19-115">See Also</span></span>


[<span data-ttu-id="37f19-116">Настройка Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37f19-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="37f19-117">Настройка политик для управления доступом федеративных пользователей XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37f19-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="37f19-118">Управление федеративными партнерами XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37f19-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="37f19-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="37f19-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="37f19-120">[Get — CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="37f19-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="37f19-121">[Get — Ксксмппгатевайконфигуратион](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="37f19-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

