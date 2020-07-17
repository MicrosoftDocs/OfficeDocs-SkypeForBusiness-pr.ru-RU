---
title: Настройка политик доступа и сертификатов шлюза XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e17634a8836a56ce7002e3d0cf57440f72c60f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="79bec-102">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="79bec-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79bec-103">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="79bec-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="79bec-p101">Федерация XMPP определяет внешнее развертывание на основе протокола XMPP. Конфигурация XMPP обеспечивает доступ пользователей Lync к пользователям домена XMPP следующими способами:</span><span class="sxs-lookup"><span data-stu-id="79bec-p101">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="79bec-106">Обмен мгновенными сообщениями и отслеживание присутствия — только личное двустороннее общение</span><span class="sxs-lookup"><span data-stu-id="79bec-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="79bec-107">Создание федеративных контактов XMPP в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="79bec-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="79bec-p102">При настройке политик для поддержки федеративных контактов по протоколу XMPP) политики применяются к пользователям федеративных доменов, но не к пользователям поставщиков услуг обмена мгновенными сообщениями по протоколу SIP (например, Windows Live) или федеративных доменов SIP. Вы настраиваете федеративного партнера XMPP для каждого федеративного домена XMPP, для которого необходимо разрешить взаимодействие и добавление контактов пользователями. После задания политик необходимо настроить сертификаты шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="79bec-p102">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79bec-111">Чтобы начать миграцию шлюза XMPP, необходимо развернуть шлюз Lync Server 2013 XMPP и настроить политики доступа, чтобы разрешить пользователям использовать шлюз Lync Server 2013 XMPP.</span><span class="sxs-lookup"><span data-stu-id="79bec-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="79bec-112">Перед выполнением этих действий все пользователи должны быть перемещены в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79bec-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="79bec-113">Дополнительные сведения: <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Настройка шлюза XMPP в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="79bec-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="79bec-114">Настройка политики внешнего доступа для разрешения доступа пользователей к шлюзу XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79bec-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="79bec-115">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79bec-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="79bec-116">На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **External Access Policy** (Политика внешнего доступа).</span><span class="sxs-lookup"><span data-stu-id="79bec-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="79bec-117">Щелкните **New** (Создать), а затем щелкните **User policy** (Пользовательская политика).</span><span class="sxs-lookup"><span data-stu-id="79bec-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="79bec-118">Введите имя для политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="79bec-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="79bec-119">Добавьте описание политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="79bec-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="79bec-120">Выберите **Enable communications with federated users** (Разрешить взаимодействие с федеративными пользователями).</span><span class="sxs-lookup"><span data-stu-id="79bec-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="79bec-121">Выберите **Enable communications with XMPP federated users** (Разрешить взаимодействие с федеративными пользователями XMPP).</span><span class="sxs-lookup"><span data-stu-id="79bec-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="79bec-122">Щелкните **Commit** (Сохранить), чтобы сохранить изменение политики сайта или пользователей.</span><span class="sxs-lookup"><span data-stu-id="79bec-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

