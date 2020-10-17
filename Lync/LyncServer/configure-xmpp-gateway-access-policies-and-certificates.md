---
title: Настройка политик доступа и сертификатов шлюза XMPP
description: Настройте политики доступа к шлюзу XMPP и сертификаты.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e958100501ad9ca87d1ab970162f4be8c7692a99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549715"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="0121a-103">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="0121a-103">Configure XMPP gateway access policies and certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0121a-104">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="0121a-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="0121a-p101">Федерация XMPP определяет внешнее развертывание на основе протокола XMPP. Конфигурация XMPP обеспечивает доступ пользователей Lync к пользователям домена XMPP следующими способами:</span><span class="sxs-lookup"><span data-stu-id="0121a-p101">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="0121a-107">Обмен мгновенными сообщениями и отслеживание присутствия — только личное двустороннее общение</span><span class="sxs-lookup"><span data-stu-id="0121a-107">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="0121a-108">Создание федеративных контактов XMPP в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="0121a-108">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="0121a-p102">При настройке политик для поддержки федеративных контактов по протоколу XMPP) политики применяются к пользователям федеративных доменов, но не к пользователям поставщиков услуг обмена мгновенными сообщениями по протоколу SIP (например, Windows Live) или федеративных доменов SIP. Вы настраиваете федеративного партнера XMPP для каждого федеративного домена XMPP, для которого необходимо разрешить взаимодействие и добавление контактов пользователями. После задания политик необходимо настроить сертификаты шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="0121a-p102">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0121a-112">Чтобы начать миграцию шлюза XMPP, необходимо развернуть шлюз Lync Server 2013 XMPP и настроить политики доступа, чтобы разрешить пользователям использовать шлюз Lync Server 2013 XMPP.</span><span class="sxs-lookup"><span data-stu-id="0121a-112">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="0121a-113">Перед выполнением этих действий все пользователи должны быть перемещены в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0121a-113">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="0121a-114">Дополнительные сведения: <A href="configure-xmpp-gateway-on-lync-server-2013.md">Настройка шлюза XMPP в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0121a-114">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="0121a-115">Настройка политики внешнего доступа для разрешения доступа пользователей к шлюзу XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0121a-115">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="0121a-116">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0121a-116">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="0121a-117">На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **External Access Policy** (Политика внешнего доступа).</span><span class="sxs-lookup"><span data-stu-id="0121a-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="0121a-118">Щелкните **New** (Создать), а затем щелкните **User policy** (Пользовательская политика).</span><span class="sxs-lookup"><span data-stu-id="0121a-118">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="0121a-119">Введите имя для политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="0121a-119">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="0121a-120">Добавьте описание политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="0121a-120">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="0121a-121">Выберите **Enable communications with federated users** (Разрешить взаимодействие с федеративными пользователями).</span><span class="sxs-lookup"><span data-stu-id="0121a-121">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="0121a-122">Выберите **Enable communications with XMPP federated users** (Разрешить взаимодействие с федеративными пользователями XMPP).</span><span class="sxs-lookup"><span data-stu-id="0121a-122">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="0121a-123">Щелкните **Commit** (Сохранить), чтобы сохранить изменение политики сайта или пользователей.</span><span class="sxs-lookup"><span data-stu-id="0121a-123">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

