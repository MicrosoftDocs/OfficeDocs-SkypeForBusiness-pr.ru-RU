---
title: Необходимые условия для обеспечения безопасности и настройки корпоративной голосовой связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="48ff5-102">Требования к безопасности и конфигурации для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48ff5-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48ff5-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="48ff5-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="48ff5-104">Убедитесь, что ваша инфраструктура отвечает следующим требованиям: безопасность, Конфигурация пользователя и особые требования к оборудованию.</span><span class="sxs-lookup"><span data-stu-id="48ff5-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="48ff5-105">Права администратора и инфраструктура сертификата</span><span class="sxs-lookup"><span data-stu-id="48ff5-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="48ff5-106">Убедитесь в том, что ваша среда настроена с помощью следующих групп пользователей и инфраструктуры сертификации для использования во время процесса корпоративного развертывания.</span><span class="sxs-lookup"><span data-stu-id="48ff5-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="48ff5-107">Администраторы, развертывающие корпоративную голосовую почту, должны быть членами группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="48ff5-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="48ff5-108">Администраторы, выполняющие задачи конфигурирования, должны обладать достаточными правами:</span><span class="sxs-lookup"><span data-stu-id="48ff5-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="48ff5-109">**CsVoiceAdministrator:** администратор с этой ролью может выполнять задачи настройки голосовой связи, управлять голосовыми приложениями и назначать голосовые политики конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="48ff5-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="48ff5-p101">**CsUserAdministrator:** администратор с этой ролью может управлять свойствами пользователей, например активацией корпоративной голосовой связи для пользователя. Этот администратор может также назначать политики на уровне пользователя за исключением политики архивирования, переносить пользователей и управлять телефонами общего пользования и аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="48ff5-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="48ff5-112">**CsAdministrator:** администратор с этой ролью может выполнять все задачи ролей CsUserAdministrator и CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48ff5-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="48ff5-113">Делегирование позволяет нескольким администраторам принять участие в развертывании Lync Server, не открывая доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="48ff5-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="48ff5-114">Развертывание и настройка управляемой ключевой инфраструктуры (MKI) осуществляются с помощью инфраструктуры Майкрософт или стороннего центра сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="48ff5-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="48ff5-115">Дополнительные сведения о требованиях к сертификатам в Lync Server можно найти в разделе <A href="lync-server-2013-certificate-infrastructure-requirements.md">требования к инфраструктуре сертификатов для Lync server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="48ff5-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="48ff5-116">Конфигурация пользователя</span><span class="sxs-lookup"><span data-stu-id="48ff5-116">User Configuration</span></span>

<span data-ttu-id="48ff5-117">Если вы состроили сервер с помощью каждого пула переднего плана или сервера Standard Edition во время клиентского развертывания, параметры пользователя, необходимые для корпоративной голосовой связи, были настроены автоматически во время установки файлов для этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="48ff5-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="48ff5-118">Если вы впервые разворачиваете корпоративную рабочую нагрузку, прежде чем приступать к развертыванию, назначьте основной номер телефона для каждого пользователя, который планируется включить для корпоративного голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="48ff5-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="48ff5-119">As the administrator, you are responsible for ensuring that this number is unique.</span><span class="sxs-lookup"><span data-stu-id="48ff5-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="48ff5-120">Прежде чем приступить к реализации, все основные номера телефонов должны быть нормализованы (правильно отформатированы) и скопированы в свойство **универсального кода ресурса (URI** ) для каждой строки пользователя с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="48ff5-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="48ff5-121">Примеры основных номеров телефонов, необходимых для развертывания корпоративной голосовой связи, приведены в статье Планирование абонентов <A href="lync-server-2013-dial-plans-and-normalization-rules.md">и правил нормализации в Lync server 2013</A> в разделе " <A href="lync-server-2013-dial-plans-and-normalization-rules.md">планы звонков и нормализации</A> " в Lync Server 2013 в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="48ff5-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="48ff5-122">Дальнейшие действия: Установка файлов и Настройка подключения PSTN</span><span class="sxs-lookup"><span data-stu-id="48ff5-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="48ff5-123">После того как вы проверите программное обеспечение и требования к среде для корпоративной голосовой связи, вы можете использовать следующие материалы:</span><span class="sxs-lookup"><span data-stu-id="48ff5-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="48ff5-124">Установите сервер-посредник, как описано в разделе [Установка сервера исправлений в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), но только в том случае, если вы хотите развернуть сервер изолированных обновлений или пул, так как серверы-исправления устанавливаются в рамках пула переднего плана или процесса развертывания сервера Standard Edition при размещении.</span><span class="sxs-lookup"><span data-stu-id="48ff5-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="48ff5-125">Кроме того, начните настраивать параметры для маршрутизации звонков для пользователей корпоративной голосовой связи, как описано в разделе [Настройка каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="48ff5-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

