---
title: "Зависимости Office 365 для Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Работа Microsoft Teams основана на Группах Office 365, SharePoint Online и OneDrive для бизнеса."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a><span data-ttu-id="70282-103">Зависимости Office 365 для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70282-103">Office 365 dependencies for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="70282-104">Microsoft Teams использует Группы Office 365 для хранения сведений о членстве в командах и других свойств, например параметров классификации данных для команд.</span><span class="sxs-lookup"><span data-stu-id="70282-104">Microsoft Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="70282-105">Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих активов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды.</span><span class="sxs-lookup"><span data-stu-id="70282-105">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

<span data-ttu-id="70282-106">Служба Teams также использует SharePoint Online и OneDrive для бизнеса, чтобы хранить файлы и документы для бесед в каналах и чате.</span><span class="sxs-lookup"><span data-stu-id="70282-106">Teams also relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="70282-107">Кроме того, Teams использует Группы Office 365 для хранения сведений о членстве в командах и других свойств, например параметров классификации данных для команд.</span><span class="sxs-lookup"><span data-stu-id="70282-107">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="70282-108">На гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="70282-108">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    
<span data-ttu-id="70282-109">Чтобы обеспечить полноценный гостевой доступ в Teams, администраторам Office 365 следует выбрать значение **Включить** для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="70282-109">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="70282-110">В SharePoint Online: **Only allow sharing with external users already in the directory (Разрешить общий доступ только с внешними пользователями, уже присутствующими в каталоге)**</span><span class="sxs-lookup"><span data-stu-id="70282-110">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="70282-111">Дополнительные сведения см. в статье [Управление внешним общим доступом для среды SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="70282-111">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="70282-112">В Группах Office 365: **Let group owners add people outside the organization to groups (Разрешить владельцам добавлять в группы людей извне организации)**</span><span class="sxs-lookup"><span data-stu-id="70282-112">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="70282-113">Дополнительные сведения см. в статье [Контроль гостевого доступа в Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="70282-113">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="70282-114">Вы можете управлять параметрами внешних пользователей SharePoint Online для подключенного к Teams сайта группы.</span><span class="sxs-lookup"><span data-stu-id="70282-114">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="70282-115">Дополнительные сведения см. в статье [Управление параметрами для сайта группы SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="70282-115">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>