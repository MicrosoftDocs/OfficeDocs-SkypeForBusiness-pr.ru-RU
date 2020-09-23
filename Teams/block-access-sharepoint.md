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
description: Сведения о том, как заблокировать доступ к SharePoint для определенных пользователей
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203842"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="56eb9-103">Блокировка доступа к SharePoint для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="56eb9-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="56eb9-104">Применение политики условного доступа (ЦС) в SharePoint в Microsoft 365 также применяется к Teams.</span><span class="sxs-lookup"><span data-stu-id="56eb9-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="56eb9-105">Тем не менее, в некоторых организациях нужно заблокировать доступ к файлам SharePoint (добавить, скачать, просмотреть, изменить, создать), но разрешить их сотрудникам использование настольных, мобильных и веб-клиентов Teams на неуправляемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="56eb9-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="56eb9-106">В соответствии с правилами политики ЦС блокировка SharePoint может также привести к блокировке групп.</span><span class="sxs-lookup"><span data-stu-id="56eb9-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="56eb9-107">В этой статье объясняется, как можно обойти это ограничение и позволить вашим сотрудникам продолжать использовать Teams и полностью блокировать доступ к файлам, хранящимся в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="56eb9-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="56eb9-108">Блокировка или ограничение доступа на неуправляемых устройствах зависит от политик условного доступа Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56eb9-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="56eb9-109">Дополнительные сведения о [лицензировании Azure AD](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="56eb9-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="56eb9-110">Общие сведения об условном доступе в Azure AD см. [в разделе условный доступ в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="56eb9-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="56eb9-111">Сведения о рекомендуемых политиках доступа SharePoint Online см. в разделе [рекомендации по политике безопасности сайтов и файлов SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="56eb9-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="56eb9-112">Если вы ограничили доступ к неуправляемым устройствам, пользователи на управляемых устройствах должны использовать одну из [поддерживаемых комбинаций ОС и браузеров](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), или они также будут иметь ограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="56eb9-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="56eb9-113">Вы можете заблокировать или ограничить доступ к:</span><span class="sxs-lookup"><span data-stu-id="56eb9-113">You can block or limit access for:</span></span>

- <span data-ttu-id="56eb9-114">Пользователи в организации или только некоторые пользователи или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="56eb9-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="56eb9-115">Все сайты в организации или только некоторые сайты.</span><span class="sxs-lookup"><span data-stu-id="56eb9-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="56eb9-116">Когда Access блокируется, пользователи увидят сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="56eb9-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="56eb9-117">Блокировка доступа обеспечивает безопасность и защищает конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="56eb9-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="56eb9-118">Когда Access блокируется, пользователи увидят сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="56eb9-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="56eb9-119">Откройте центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="56eb9-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="56eb9-120">**Разворачивание политик**  >  **доступа**.</span><span class="sxs-lookup"><span data-stu-id="56eb9-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="56eb9-121">В разделе **неуправляемые устройства** выберите команду **блокировать доступ** и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="56eb9-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![раздел "неуправляемые устройства" для политик](media/no-sharepoint-access1.png)

4. <span data-ttu-id="56eb9-123">Откройте портал [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) и перейдите в раздел **политики условного доступа**.</span><span class="sxs-lookup"><span data-stu-id="56eb9-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="56eb9-124">Вы увидите, что SharePoint создал новую политику, которая похожа на приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="56eb9-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![Новая политика с именем использование ограничений, наложенных приложением, для доступа к браузеру](media/no-sharepoint-access2.png)

5. <span data-ttu-id="56eb9-126">Обновление политики для назначения только определенным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="56eb9-126">Update the policy to target only specific users or a group.</span></span>

    ![Центр администрирования SharePoint с выделенной секцией выбора пользователя.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="56eb9-128">Если вы настраиваете этот параметр политики, ваш доступ к порталу администрирования SharePoint будет сокращен.</span><span class="sxs-lookup"><span data-stu-id="56eb9-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="56eb9-129">Рекомендуется настроить политику исключений и выбрать глобальную группу и администраторов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="56eb9-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="56eb9-130">Проверка того, что выбрано только SharePoint в качестве целевого облачного приложения</span><span class="sxs-lookup"><span data-stu-id="56eb9-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![В качестве целевого приложения выбрано SharePoint.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="56eb9-132">Обновите **условия** , чтобы включить настольные клиенты.</span><span class="sxs-lookup"><span data-stu-id="56eb9-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![выделены настольные и мобильные приложения.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="56eb9-134">Убедитесь, что включен **доступ для предоставления доступа**</span><span class="sxs-lookup"><span data-stu-id="56eb9-134">Make sure that **Grant access** is enabled</span></span>

    ![разрешение на предоставление доступа разрешено.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="56eb9-136">Убедитесь в том, что **функция использования принудительных ограничений приложения** включена.</span><span class="sxs-lookup"><span data-stu-id="56eb9-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="56eb9-137">Включите политику и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="56eb9-137">Enable your policy and select **Save**.</span></span>

    ![Принудительные ограничения, примененные к приложению, включены.](media/no-sharepoint-access6.png)

<span data-ttu-id="56eb9-139">Для проверки политики необходимо выйти из любого клиента, например из классического приложения Teams или клиента синхронизации OneDrive для бизнеса, и войти в систему еще раз, чтобы убедиться в том, что политика работает.</span><span class="sxs-lookup"><span data-stu-id="56eb9-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="56eb9-140">Если ваш доступ заблокирован, вы увидите сообщение в Teams, в котором указано, что элемент может отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="56eb9-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Сообщение "элемент не найден".](media/access-denied-sharepoint.png)

<span data-ttu-id="56eb9-142">В SharePoint вы получите сообщение об отказе в доступе.</span><span class="sxs-lookup"><span data-stu-id="56eb9-142">In Sharepoint, you'll receive an access denied message.</span></span>

![Сообщение об отказе в доступе.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="56eb9-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="56eb9-144">Related topics</span></span>

[<span data-ttu-id="56eb9-145">Управление доступом к неуправляемым устройствам в SharePoint</span><span class="sxs-lookup"><span data-stu-id="56eb9-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
