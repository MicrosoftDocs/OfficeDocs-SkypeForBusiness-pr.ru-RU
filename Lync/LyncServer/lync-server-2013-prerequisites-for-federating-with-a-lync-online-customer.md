---
title: 'Lync Server 2013: предварительные требования для Федерации с клиентом Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af3db1918e2d347084f1bbdcdf5ea4eb92ae8d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="ecfea-102">Необходимые условия для Федерации с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecfea-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecfea-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ecfea-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ecfea-104">Чтобы создать федерацию с заказчиком Lync Online 2010, вы должны уже выполнить начальное развертывание и настройку Lync Server 2013 в своей организации.</span><span class="sxs-lookup"><span data-stu-id="ecfea-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="ecfea-105">Доступны следующие политики:</span><span class="sxs-lookup"><span data-stu-id="ecfea-105">This includes the following:</span></span>

  - <span data-ttu-id="ecfea-106">Развертывание по крайней мере одного стандартного сервера выпуска или одного пула переднего плана Enterprise Edition в Организации.</span><span class="sxs-lookup"><span data-stu-id="ecfea-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="ecfea-107">Дополнительные сведения о развертывании внутренних серверов можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ecfea-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ecfea-108">Включение внутренних учетных записей пользователей для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecfea-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="ecfea-109">Дополнительные сведения можно найти в разделе [Отключение и повторное включение учетной записи пользователя для Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="ecfea-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="ecfea-110">Развертывание по крайней мере одного пограничного сервера и других компонентов, необходимых для поддержки внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="ecfea-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="ecfea-111">Подробные сведения можно найти в разделе [Управление интеграцией и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ecfea-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ecfea-112">Включение поддержки Федерации в Организации и настройка соответствующего метода для управления доступом с помощью федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="ecfea-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="ecfea-113">Дополнительные сведения можно найти в разделе [Включение и отключение удаленного доступа пользователей в Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) и [Управление поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="ecfea-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="ecfea-114">Разрешение доступа внешних пользователей для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ecfea-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="ecfea-115">Дополнительные сведения можно найти в разделе [назначение внешней политики доступа к пользователю Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) , а также в документации по развертыванию или работе.</span><span class="sxs-lookup"><span data-stu-id="ecfea-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

