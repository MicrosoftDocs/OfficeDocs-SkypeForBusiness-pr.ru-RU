---
title: Настройка политик доступа и сертификатов шлюза XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Федерация XMPP определяет внешнее развертывание на основе протокола XMPP. Конфигурация XMPP позволяет пользователям получать доступ к пользователям домена XMPP с помощью:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753939"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="6fe65-104">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="6fe65-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="6fe65-105">Федерация XMPP определяет внешнее развертывание на основе протокола XMPP.</span><span class="sxs-lookup"><span data-stu-id="6fe65-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="6fe65-106">Конфигурация XMPP позволяет пользователям получать доступ к пользователям домена XMPP с помощью:</span><span class="sxs-lookup"><span data-stu-id="6fe65-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="6fe65-107">Im and Presence - person to person only</span><span class="sxs-lookup"><span data-stu-id="6fe65-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="6fe65-108">Создание федераированных контактов XMPP в клиенте Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6fe65-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="6fe65-109">При настройке политик для поддержки федераированных XMPP-партнеров эти политики применяются к пользователям федераированных доменов XMPP, но не к пользователям поставщиков службы мгновенных сообщений (IM) протокола SIP или федераированных доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="6fe65-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="6fe65-110">Настраивается федераированный XMPP-партнер для каждого федератного домена XMPP, с помощью которых пользователи могут добавлять контакты и взаимодействовать.</span><span class="sxs-lookup"><span data-stu-id="6fe65-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="6fe65-111">После задания политик необходимо настроить сертификаты шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="6fe65-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6fe65-112">Функции XMPP нерекомендовать в Skype для бизнеса Server 2019, но могут быть продолжены на устаревшем сервере в сосуществовании со Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6fe65-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="6fe65-113">Убедитесь, что вы уже развернули устаревший сервер (Skype для бизнеса Server 2015 / Lync Server 2013) XMPP Gateway и настроили политики доступа, чтобы пользователи могли использовать устаревший шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="6fe65-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="6fe65-114">Подробные сведения [см. в подтипе "Миграция федерации XMPP".](migrating-xmpp-federation.md)</span><span class="sxs-lookup"><span data-stu-id="6fe65-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="6fe65-115">Настройка политики внешнего доступа для присоединения пользователей к устаревшему шлюзу XMPP</span><span class="sxs-lookup"><span data-stu-id="6fe65-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="6fe65-116">Откройте устаревшую панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6fe65-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6fe65-117">На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **External Access Policy** (Политика внешнего доступа).</span><span class="sxs-lookup"><span data-stu-id="6fe65-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="6fe65-118">Нажмите кнопку **Создать** и щелкните **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="6fe65-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="6fe65-119">Введите имя для политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="6fe65-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="6fe65-120">Добавьте описание политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="6fe65-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="6fe65-121">Выберите **Enable communications with federated users** (Разрешить взаимодействие с федеративными пользователями).</span><span class="sxs-lookup"><span data-stu-id="6fe65-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="6fe65-122">Выберите **Enable communications with XMPP federated users** (Разрешить взаимодействие с федеративными пользователями XMPP).</span><span class="sxs-lookup"><span data-stu-id="6fe65-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="6fe65-123">Щелкните **Commit** (Сохранить), чтобы сохранить изменение политики сайта или пользователей.</span><span class="sxs-lookup"><span data-stu-id="6fe65-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

