---
title: Планирование интеграции расширенной службы обмена сообщениями и протоколом присутствия (КСМПП)
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
ms.openlocfilehash: 5ee0543d36cb43a05042ca4341a837ae10b52051
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="69647-102">Планирование Федерации протоколов обмена сообщениями и присутствия в КСМПП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69647-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69647-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="69647-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="69647-104">Предыдущие версии Lync Server и Office Communications Server предоставили шлюз расширенных сообщений и протоколов доступа (КСМПП), который можно развернуть как отдельную серверную роль, разрешающую Федерацию с помощью КСМППных развертываний.</span><span class="sxs-lookup"><span data-stu-id="69647-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="69647-105">В Microsoft Lync Server 2013 функциональность КСМПП может быть развернута как функция.</span><span class="sxs-lookup"><span data-stu-id="69647-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="69647-106">Функции КСМПП устанавливаются в двух частях: прокси-сервер КСМПП, который работает на пограничном сервере и шлюз КСМПП, который работает на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="69647-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="69647-107">Развертывание и настройка КСМПП рассматривается при [развертывании внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) вы планируете поддерживать КСМПП в вашей организации, определяя правила порта и протоколов в брандмауэре, настройку сертификатов и добавление записей DNS.</span><span class="sxs-lookup"><span data-stu-id="69647-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="69647-108">В следующих разделах приведены сведения о том, как вам потребуется успешно спланировать КСМПП Федерацию для развертывания.</span><span class="sxs-lookup"><span data-stu-id="69647-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="69647-p103">Возможность XMPP сервера Lync Server 2013 была протестирована корпорацией Microsoft и поддерживается в части федеративного обмена мгновенными сообщениями с использованием Google Talk. По вопросам использования других XMPP-систем обращайтесь к сторонним поставщикам, чтобы выяснить, поддерживают ли они федерацию с Lync Server 2013, а также чтобы получить рекомендации по вопросам, связанным с устранением неполадок и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="69647-p103">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69647-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="69647-111">In This Section</span></span>

  - [<span data-ttu-id="69647-112">Сведения о сертификате — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69647-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="69647-113">Сводка по порту — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69647-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="69647-114">Общие сведения о DNS — расширяемая Федерация протоколов обмена сообщениями и доступности КСМПП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69647-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69647-115">См. также</span><span class="sxs-lookup"><span data-stu-id="69647-115">See Also</span></span>


[<span data-ttu-id="69647-116">Настройка федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69647-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="69647-117">Настройка политик управления доступом федеративных XMPP-пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69647-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="69647-118">Управление федеративными XMPP-партнерами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69647-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="69647-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="69647-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="69647-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="69647-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="69647-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="69647-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

