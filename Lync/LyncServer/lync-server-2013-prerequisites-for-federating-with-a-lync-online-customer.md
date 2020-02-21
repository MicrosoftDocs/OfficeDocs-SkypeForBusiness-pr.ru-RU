---
title: 'Lync Server 2013: необходимые условия для Федерации с клиентом Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa1dbaf69aecc7977737317cccc4c6ac6bb07d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="ef3a3-102">Необходимые условия для Федерации с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef3a3-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef3a3-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ef3a3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ef3a3-104">Для Федерации с клиентом Lync Online 2010 вы должны уже выполнить начальное развертывание и настройку Lync Server 2013 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="ef3a3-105">Эта кнопка предоставляет доступ ко следующим командам:</span><span class="sxs-lookup"><span data-stu-id="ef3a3-105">This includes the following:</span></span>

  - <span data-ttu-id="ef3a3-106">Развертывание по крайней мере одного сервера Standard Edition или пула переднего плана Enterprise Edition в Организации.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="ef3a3-107">Дополнительные сведения о развертывании внутренних серверов приведены в статье Deployment [Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ef3a3-108">Включение внутренних учетных записей пользователей для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="ef3a3-109">Для получения дополнительных сведений см. раздел [Отключение или повторное включение учетной записи пользователя для Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="ef3a3-110">Развертывание по крайней мере одного пограничного сервера и других компонентов, необходимых для поддержки доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="ef3a3-111">Дополнительные сведения см в статье [Управление федерациями и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ef3a3-112">Активация поддержки федераций в организации и настройка надлежащего метода управлением доступа к федеративным доменам.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="ef3a3-113">Дополнительные сведения см. в статье [Включение или отключение удаленного доступа пользователей в Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) и [Управление ФЕДЕРАТИВНЫМИ поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="ef3a3-114">Активация внешнего доступа для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="ef3a3-115">Дополнительные сведения: [Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) , документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="ef3a3-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

