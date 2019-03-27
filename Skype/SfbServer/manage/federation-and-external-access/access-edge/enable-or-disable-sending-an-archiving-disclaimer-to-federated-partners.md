---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 859b4e295a90fd44ce69efe4af7daa63ddc8812c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885321"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="3d985-102">Включение и отключение отправки федеративным партнерам Скайп заявление об отказе для архивации для Business Server</span><span class="sxs-lookup"><span data-stu-id="3d985-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="3d985-103">Во время развертывания пограничных серверов и поддержкой федерации для вашей организации должны указаны следует ли автоматически отправлять от архивирования федеративным партнерам.</span><span class="sxs-lookup"><span data-stu-id="3d985-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="3d985-104">Если архивация внешних коммуникаций, следует включить отправки отказа от архивирования.</span><span class="sxs-lookup"><span data-stu-id="3d985-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="3d985-105">Используйте описанную в этом разделе для изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3d985-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="3d985-106">В следующей процедуре предполагается, что вы уже включен федерации для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3d985-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="3d985-107">Для получения дополнительных сведений о включении федерации видеть [включения или отключения удаленного доступа пользователей](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3d985-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="3d985-108">Включение и отключение отправки отказа от архивирования федеративным партнерам</span><span class="sxs-lookup"><span data-stu-id="3d985-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="3d985-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3d985-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d985-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3d985-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3d985-111">В левой панели навигации щелкните **Доступ для внешних пользователей**, **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="3d985-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3d985-112">На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="3d985-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3d985-113">В разделе **Изменить настройку пограничного доступа**, в разделе **Разрешить связь с федеративными пользователями**установите или снимите флажок **отправлять уведомление об федеративным партнерам архивации** для включения или отключения автоматически отправляя архивации Заявление об отказе.</span><span class="sxs-lookup"><span data-stu-id="3d985-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="3d985-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="3d985-114">Click **Commit**.</span></span>

<span data-ttu-id="3d985-115">Чтобы разрешить федеративным пользователям совместно работать с пользователями в вашей Скайп для развертывания Business Server, необходимо также настроить по крайней мере одной политики внешнего доступа для поддержки доступа федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3d985-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="3d985-116">Для получения дополнительных сведений о контроле доступа для определенных федеративных доменов в статье [Configure поддержки для разрешенных внешних доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="3d985-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3d985-117">Включение или отключение архивации заявление об отказе с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d985-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3d985-118">Использование от архивирования можно управлять с помощью командлета Set-CsAccessEdgeConfiguration и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d985-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3d985-119">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d985-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="3d985-120">Включение архивации заявление об отказе</span><span class="sxs-lookup"><span data-stu-id="3d985-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="3d985-121">Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="3d985-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="3d985-122">Для отключения от архивирования</span><span class="sxs-lookup"><span data-stu-id="3d985-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="3d985-123">Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="3d985-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


