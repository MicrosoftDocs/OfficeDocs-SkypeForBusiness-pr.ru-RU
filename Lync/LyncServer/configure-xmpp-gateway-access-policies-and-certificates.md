---
title: Настройка политик доступа и сертификатов шлюза XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f545fd7681e492440419aee600635858bf7bfdef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="59f5c-102">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="59f5c-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59f5c-103">_**Тема последнего изменения:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="59f5c-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="59f5c-104">КСМПП Федерация определяет внешнее развертывание на основе расширяемого протокола обмена сообщениями и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="59f5c-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="59f5c-105">Конфигурация КСМПП позволяет пользователям Lync получать доступ к КСМПП доменам, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="59f5c-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="59f5c-106">Обмен сообщениями и присутствие — только для человека</span><span class="sxs-lookup"><span data-stu-id="59f5c-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="59f5c-107">Создание федеративных контактов КСМПП в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="59f5c-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="59f5c-108">Если вы настраиваете политики для поддержки федеративных партнеров по протоколу расширенного обмена сообщениями (КСМПП), политики применяются к пользователям КСМПП федеративных доменов, но не к пользователям служб мгновенных сообщений в протоколе запуска сеансов (SIP). (например, Windows Live) или федеративные домены SIP.</span><span class="sxs-lookup"><span data-stu-id="59f5c-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="59f5c-109">Вы настраиваете федеративного партнера КСМПП для каждого КСМПП федеративного домена, с которым вы хотите разрешить пользователям добавлять контакты и взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="59f5c-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="59f5c-110">После того как политики будут установлены, необходимо настроить сертификаты шлюза КСМПП.</span><span class="sxs-lookup"><span data-stu-id="59f5c-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59f5c-111">Чтобы начать миграцию шлюза КСМПП, необходимо развернуть шлюз Lync Server 2013 КСМПП и настроить политики доступа, чтобы включить пользователей для Lync Server 2013 КСМПП Gateway.</span><span class="sxs-lookup"><span data-stu-id="59f5c-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="59f5c-112">Перед выполнением описанных ниже действий необходимо переместить всех пользователей в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59f5c-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="59f5c-113">Подробности можно найти <A href="configure-xmpp-gateway-on-lync-server-2013.md">в разделе Настройка шлюза КСМПП на Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="59f5c-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="59f5c-114">Настройка политики внешнего доступа для поддержки пользователей Lync Server 2013 КСМПП Gateway</span><span class="sxs-lookup"><span data-stu-id="59f5c-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="59f5c-115">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59f5c-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="59f5c-116">На панели навигации слева выберите пункт **интеграция и внешний доступ**, а затем — **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="59f5c-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="59f5c-117">Нажмите кнопку **создать** , а затем выберите пункт **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="59f5c-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="59f5c-118">Введите имя для политики пользователей внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="59f5c-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="59f5c-119">Введите описание для политики пользователей внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="59f5c-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="59f5c-120">Выберите **включить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="59f5c-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="59f5c-121">Выберите **включить связь с федеративными пользователями КСМПП**.</span><span class="sxs-lookup"><span data-stu-id="59f5c-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="59f5c-122">Нажмите \*\*\*\* кнопку Сохранить, чтобы сохранить изменения в политике сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="59f5c-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

