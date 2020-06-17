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
description: 'Федерация XMPP определяет внешнее развертывание на основе протокола XMPP. Конфигурация XMPP позволяет пользователям получать доступ к пользователям домена XMPP, выполнив следующие действия:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753939"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="a2be0-104">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="a2be0-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="a2be0-105">Федерация XMPP определяет внешнее развертывание на основе протокола XMPP.</span><span class="sxs-lookup"><span data-stu-id="a2be0-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="a2be0-106">Конфигурация XMPP позволяет пользователям получать доступ к пользователям домена XMPP, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a2be0-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="a2be0-107">Мгновенные сообщения и сведения о присутствии — только пользователю</span><span class="sxs-lookup"><span data-stu-id="a2be0-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="a2be0-108">Создание федеративных контактов XMPP в клиенте Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2be0-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="a2be0-109">При настройке политик для поддержки федеративных партнеров XMPP политики применяются к пользователям федеративных доменов XMPP, но не к пользователям служб службы обмена мгновенными сообщениями протокола SIP или федеративных доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="a2be0-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="a2be0-110">Вы настраиваете федеративный партнер XMPP для каждого федеративного домена XMPP, который вы хотите разрешить пользователям добавлять контакты и общаться с.</span><span class="sxs-lookup"><span data-stu-id="a2be0-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="a2be0-111">После задания политик необходимо настроить сертификаты шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="a2be0-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a2be0-112">Функции XMPP не рекомендуются в Skype для бизнеса Server 2019, но их можно продолжать использовать в устаревшем сервере в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2be0-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="a2be0-113">Убедитесь, что вы уже развернули старый сервер (Skype для бизнеса Server 2015/Lync Server 2013) XMPP Gateway и настроили политики доступа, чтобы разрешить пользователям устаревших шлюзов XMPP.</span><span class="sxs-lookup"><span data-stu-id="a2be0-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="a2be0-114">Дополнительные сведения см. в статье [Миграция Федерации XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="a2be0-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="a2be0-115">Настройка политики внешнего доступа для предоставления пользователям устаревшего шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="a2be0-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="a2be0-116">Откройте устаревшую панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a2be0-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a2be0-117">На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **External Access Policy** (Политика внешнего доступа).</span><span class="sxs-lookup"><span data-stu-id="a2be0-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="a2be0-118">Нажмите кнопку **Создать** и щелкните **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="a2be0-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="a2be0-119">Введите имя для политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="a2be0-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="a2be0-120">Добавьте описание политики внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="a2be0-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="a2be0-121">Выберите **Enable communications with federated users** (Разрешить взаимодействие с федеративными пользователями).</span><span class="sxs-lookup"><span data-stu-id="a2be0-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="a2be0-122">Выберите **Enable communications with XMPP federated users** (Разрешить взаимодействие с федеративными пользователями XMPP).</span><span class="sxs-lookup"><span data-stu-id="a2be0-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="a2be0-123">Щелкните **Commit** (Сохранить), чтобы сохранить изменение политики сайта или пользователей.</span><span class="sxs-lookup"><span data-stu-id="a2be0-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

