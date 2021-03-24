---
title: Блокировка доступа к SharePoint для определенных пользователей
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте о блокировке доступа к SharePoint для определенных пользователей
ms.openlocfilehash: dce6581abe4fee70a6622817be7aefb0e3379e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092897"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="edd60-103">Блокировка доступа к SharePoint для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="edd60-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="edd60-104">Применение политики условного доступа в SharePoint в Microsoft 365 также обеспечивает ее применение в Teams.</span><span class="sxs-lookup"><span data-stu-id="edd60-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="edd60-105">Некоторые организации хотят блокировать доступ к файлам SharePoint (отправка, скачивание, просмотр, изменение, создание), но разрешать своим сотрудникам использовать классические, мобильные и веб-клиенты Teams на неуправляемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="edd60-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="edd60-106">В рамках правил политики условного доступа блокировка SharePoint также приведет к блокировке Teams.</span><span class="sxs-lookup"><span data-stu-id="edd60-106">Under the CA policy rules, blocking SharePoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="edd60-107">В этой статье описано, как обойти это ограничение и разрешить своим сотрудникам продолжать использование Teams при полной блокировке доступа к файлам, хранящимся в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="edd60-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="edd60-108">Для блокирования или ограничения доступа на неуправляемых устройствах применяются политики условного доступа Azure AD.</span><span class="sxs-lookup"><span data-stu-id="edd60-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="edd60-109">Сведения о [лицензировании Azure AD](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="edd60-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="edd60-110">Общие сведения о условном доступе в Azure AD см. в статье [Условный доступ в Azure Active Directory](/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="edd60-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="edd60-111">Сведения о рекомендуемых политиках доступа SharePoint Online см. в статье рекомендации по [Рекомендации политики по защите сайтов и файлов SharePoint](/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="edd60-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="edd60-112">Если вы ограничили доступ на неуправляемых устройствах, пользователи управляемых устройств должны использовать [поддерживаемые сочетания ОС и браузера](/azure/active-directory/conditional-access/technical-reference#client-apps-condition) или их доступ также будет ограничен.</span><span class="sxs-lookup"><span data-stu-id="edd60-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="edd60-113">Можно заблокировать или ограничить доступ:</span><span class="sxs-lookup"><span data-stu-id="edd60-113">You can block or limit access for:</span></span>

- <span data-ttu-id="edd60-114">для сотрудников организации или только для некоторых пользователей либо групп безопасности;</span><span class="sxs-lookup"><span data-stu-id="edd60-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="edd60-115">ко всем сайтам организации или только к некоторым сайтам.</span><span class="sxs-lookup"><span data-stu-id="edd60-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="edd60-116">Если доступ заблокирован, пользователь увидит сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="edd60-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="edd60-117">Блокировка доступа помогает обеспечить безопасность и защищает конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="edd60-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="edd60-118">Если доступ заблокирован, пользователь увидит сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="edd60-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="edd60-119">Откройте Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="edd60-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="edd60-120">Разверните **Политики** > **Политики доступа**.</span><span class="sxs-lookup"><span data-stu-id="edd60-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="edd60-121">В разделе **Неуправляемые устройства** выберите **Блокировать доступ** и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="edd60-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![раздел неуправляемых устройств для политик](media/no-sharepoint-access1.png)

4. <span data-ttu-id="edd60-123">Откройте портал [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) и перейдите в **Политики условного доступа**.</span><span class="sxs-lookup"><span data-stu-id="edd60-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="edd60-124">Вы увидите новую политику, созданную приложением SharePoint, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="edd60-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![новая политика под названием "Использование ограничений на основе приложений для доступа браузера"](media/no-sharepoint-access2.png)

5. <span data-ttu-id="edd60-126">Обновите политику, чтобы назначить ее только определенным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="edd60-126">Update the policy to target only specific users or a group.</span></span>

    ![Центр администрирования SharePoint с выделенным разделом выбора пользователей.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="edd60-128">Настройка этой политики запретит вам доступ к порталу администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="edd60-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="edd60-129">Рекомендуем настроить политику исключения и выбрать глобальных администраторов и администраторов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="edd60-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="edd60-130">В качестве конечного облачного приложения выберите только SharePoint</span><span class="sxs-lookup"><span data-stu-id="edd60-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![В качестве конечного приложения выбрано приложение SharePoint.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="edd60-132">Обновите **Условия**, чтобы добавить классические клиенты.</span><span class="sxs-lookup"><span data-stu-id="edd60-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![выделенные классические и мобильные приложения.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="edd60-134">Включите **Предоставление доступа**</span><span class="sxs-lookup"><span data-stu-id="edd60-134">Make sure that **Grant access** is enabled</span></span>

    ![предоставление доступа включено.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="edd60-136">Включите **Использовать ограничения на основе приложений**.</span><span class="sxs-lookup"><span data-stu-id="edd60-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="edd60-137">Включите свою политику и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="edd60-137">Enable your policy and select **Save**.</span></span>

    ![Ограничения на основе приложений включены.](media/no-sharepoint-access6.png)

<span data-ttu-id="edd60-139">Чтобы протестировать политику, вам требуется выйти из любого клиента, например из классического приложения Teams или клиента синхронизации OneDrive для бизнеса, а затем снова войти, чтобы увидеть работу политики.</span><span class="sxs-lookup"><span data-stu-id="edd60-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="edd60-140">Если ваш доступ заблокирован, в Teams появится сообщение о том, что элемент может отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="edd60-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Сообщение о том, что элемент не найден.](media/access-denied-sharepoint.png)

<span data-ttu-id="edd60-142">В SharePoint появится сообщение об отказе в доступе.</span><span class="sxs-lookup"><span data-stu-id="edd60-142">In SharePoint, you'll receive an access denied message.</span></span>

![Сообщение об отказе в доступе.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="edd60-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="edd60-144">Related topics</span></span>

[<span data-ttu-id="edd60-145">Управление доступом для неуправляемым устройств в SharePoint</span><span class="sxs-lookup"><span data-stu-id="edd60-145">Control access for unmanaged devices in SharePoint</span></span>](/sharepoint/control-access-from-unmanaged-devices)