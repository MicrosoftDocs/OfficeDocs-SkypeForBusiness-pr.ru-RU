---
title: "Управление гостевым доступом для Microsoft Teams"
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "ИТ-администраторы могут добавлять гостей на уровне клиента, задавать политики и разрешения для гостевых пользователей и управлять ими, определять, какие пользователи могут приглашать гостей, а также составлять отчеты о деятельности гостевых пользователей."
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed42a6f4578786f6f5ed9683cf92c3b915653d66
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
<a name="manage-guest-access-to-microsoft-teams"></a><span data-ttu-id="398b4-103">Управление гостевым доступом для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="398b4-103">Manage guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="398b4-104">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="398b4-104">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="398b4-105">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="398b4-105">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="398b4-106">Функция гостевого доступа Teams действует на уровне клиента и по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="398b4-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="398b4-107">ИТ-администраторы могут добавлять гостей на уровне клиента, задавать политики и разрешения для гостевых пользователей и управлять ими, определять, какие пользователи могут приглашать гостей, а также составлять отчеты о деятельности гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="398b4-107">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="398b4-108">Эти средства управления доступны в Центре администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="398b4-108">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="398b4-109">На контент и деятельность гостевых пользователей распространяются те же меры обеспечения соответствия и аудиторской защиты, что и на остальную часть Office 365.</span><span class="sxs-lookup"><span data-stu-id="398b4-109">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="398b4-110">Параметр клиента для гостевого доступа Teams запрещает только вход гостей.</span><span class="sxs-lookup"><span data-stu-id="398b4-110">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="398b4-111">Владельцы смогут приглашать в свои команды новых гостей и гостей из существующих каталогов.</span><span class="sxs-lookup"><span data-stu-id="398b4-111">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="398b4-112">Следует напомнить, что продукт Teams всегда учитывает внешние параметры Azure Active Directory при разрешении или запрете добавления гостя в клиент.</span><span class="sxs-lookup"><span data-stu-id="398b4-112">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="398b4-113">Кроме того, для управления гостями и их доступом к ресурсам Office 365 и Teams вы можете использовать портал Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="398b4-113">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="398b4-114">Функция гостевого доступа использует возможности службы совместной работы бизнес-бизнес (B2B) Azure Active Directory в качестве базовой инфраструктуры, чтобы хранить, например, свойства удостоверений, сведения о членстве и параметры многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="398b4-114">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="398b4-115">Дополнительные сведения об Azure Active Directory B2B см. в статьях [Что такое служба совместной работы Azure AD B2B?](https://go.microsoft.com/fwlink/p/?linkid=853011) и [Вопросы и ответы по службе совместной работы Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).</span><span class="sxs-lookup"><span data-stu-id="398b4-115">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  