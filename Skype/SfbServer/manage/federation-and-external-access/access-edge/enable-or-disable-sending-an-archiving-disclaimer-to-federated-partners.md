---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 889716377f89e2657adcd6e32c9077b8124e20c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818360"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="14699-102">Включение и отключение отправки заявления об отказе на архивацию федеративных партнеров в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="14699-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="14699-103">На момент развертывания пограничных серверов и включения Федерации для Организации необходимо указать, следует ли автоматически отправлять заявление об отказе от архивации федеративным партнерам.</span><span class="sxs-lookup"><span data-stu-id="14699-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="14699-104">При архивации внешних данных необходимо включить отправку сообщений об отказе в архивацию.</span><span class="sxs-lookup"><span data-stu-id="14699-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="14699-105">Чтобы изменить конфигурацию, воспользуйтесь процедурой, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="14699-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="14699-106">В описанной ниже процедуре предполагается, что вы уже включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="14699-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="14699-107">Дополнительные сведения о включении Федерации можно найти в разделе [Включение и отключение удаленного доступа пользователей](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="14699-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="14699-108">Включение и отключение отправки запроса на архивацию федеративных партнеров</span><span class="sxs-lookup"><span data-stu-id="14699-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="14699-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="14699-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="14699-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="14699-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="14699-111">На панели навигации слева выберите **внешний пользовательский доступ**, а затем — **Конфигурация Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="14699-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="14699-112">На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="14699-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="14699-113">В диалоговом окне **изменение конфигурации Edge для доступа**в разделе **включить связь с федеративными пользователями**установите или снимите флажок **отправлять заявление об отказе от работы федеративным партнерам** , чтобы включить или отключить автоматическую отправку сообщений об отказе в архивацию.</span><span class="sxs-lookup"><span data-stu-id="14699-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="14699-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="14699-114">Click **Commit**.</span></span>

<span data-ttu-id="14699-115">Чтобы пользователи федеративных пользователей могли работать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="14699-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="14699-116">Дополнительные сведения об управлении доступом для определенных федеративных доменов см. в разделе [Настройка поддержки для разрешенных внешних доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="14699-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="14699-117">Включение и отключение отказа от архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14699-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="14699-118">Для управления использованием отказа в архивации можно использовать Windows PowerShell и командлет Set-Ксакцесседжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="14699-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="14699-119">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14699-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="14699-120">Включение отказа в архивации</span><span class="sxs-lookup"><span data-stu-id="14699-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="14699-121">Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="14699-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="14699-122">Отключение отказа от архивации</span><span class="sxs-lookup"><span data-stu-id="14699-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="14699-123">Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="14699-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


