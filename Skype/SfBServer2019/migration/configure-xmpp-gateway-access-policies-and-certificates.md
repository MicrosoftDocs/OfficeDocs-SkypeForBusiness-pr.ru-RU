---
title: Настройка политик доступа и сертификатов шлюза XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Федерация XMPP определяет внешний развертывания, основываясь на расширяемой системы обмена сообщениями и присутствия протокола XMPP. Конфигурации XMPP позволяет пользователям получить доступ к пользователей домена XMPP с:'
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889975"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="d0f92-104">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="d0f92-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="d0f92-105">Федерация XMPP определяет внешний развертывания, основываясь на расширяемой системы обмена сообщениями и присутствия протокола XMPP.</span><span class="sxs-lookup"><span data-stu-id="d0f92-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="d0f92-106">Конфигурации XMPP позволяет пользователям получить доступ к пользователей домена XMPP с:</span><span class="sxs-lookup"><span data-stu-id="d0f92-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="d0f92-107">Обмен мгновенными Сообщениями и сведениями о присутствии — только в двустороннем режиме</span><span class="sxs-lookup"><span data-stu-id="d0f92-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="d0f92-108">Создание федеративных XMPP контактов в Скайп для бизнеса клиента</span><span class="sxs-lookup"><span data-stu-id="d0f92-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="d0f92-109">При настройке политик для поддержки XMPP федеративных партнеров, политики применяются к пользователям XMPP федеративных доменов, но не для пользователей из сеанса initiation protocol (SIP), обмен мгновенными сообщениями службы обмена Мгновенными сообщениями поставщики или SIP федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="d0f92-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="d0f92-110">Настройка федеративного партнера XMPP для каждого федеративного домена XMPP, чтобы разрешить пользователям добавлять контакты и общаться с.</span><span class="sxs-lookup"><span data-stu-id="d0f92-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="d0f92-111">Как только они на месте, необходимо настроить сертификатов шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="d0f92-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d0f92-112">Функциональные возможности XMPP рекомендуется использовать в Скайп для Business Server 2019, но может быть продолжен в устаревшем сервере в режиме сосуществования с Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d0f92-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="d0f92-113">Убедитесь, что вы уже развернули устаревшего сервера (Скайп для Business Server 2015 и Lync Server 2013) шлюза XMPP и настройки политики доступа, чтобы включить пользователей для устаревших шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="d0f92-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="d0f92-114">Дополнительные сведения см [Перенос федерации XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="d0f92-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="d0f92-115">Настройте политику внешнего доступа, чтобы разрешить пользователям для устаревших шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="d0f92-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="d0f92-116">Откройте прежних версий Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="d0f92-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="d0f92-117">В левой панели навигации щелкните **Федерация и внешний доступ**и нажмите кнопку **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="d0f92-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="d0f92-118">Нажмите кнопку **Создать** и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="d0f92-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="d0f92-119">Введите имя для политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="d0f92-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="d0f92-120">Предоставьте описание политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="d0f92-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="d0f92-121">Установите флажок **Разрешить взаимодействие с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="d0f92-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="d0f92-122">Выберите **Разрешить связь с федеративными XMPP пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d0f92-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="d0f92-123">Нажмите кнопку **зафиксировать** , чтобы сохранить изменения в политике сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="d0f92-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

