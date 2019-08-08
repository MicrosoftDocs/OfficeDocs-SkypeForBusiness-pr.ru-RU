---
title: Настройка политик доступа и сертификатов шлюза XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'КСМПП Федерация определяет внешнее развертывание на основе расширяемого протокола обмена сообщениями и присутствия (КСМПП). Конфигурация КСМПП позволяет пользователям получать доступ к КСМПП доменам, выполнив следующие действия:'
ms.openlocfilehash: 01adcbe06718068e84844f704858e04198b197b2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239293"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="950bc-104">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="950bc-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="950bc-105">КСМПП Федерация определяет внешнее развертывание на основе расширяемого протокола обмена сообщениями и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="950bc-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="950bc-106">Конфигурация КСМПП позволяет пользователям получать доступ к КСМПП доменам, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="950bc-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="950bc-107">Обмен сообщениями и присутствие — человек только для человека</span><span class="sxs-lookup"><span data-stu-id="950bc-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="950bc-108">Создание федеративных контактов КСМПП в клиенте Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="950bc-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="950bc-109">При настройке политик для поддержки федеративных партнеров КСМПП политики применяются к пользователям КСМПП федеративных доменов, но не к пользователям служб мгновенных сообщений в протоколе SIP и Федеративных доменам SIP.</span><span class="sxs-lookup"><span data-stu-id="950bc-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="950bc-110">Вы настраиваете федеративного партнера КСМПП для каждого КСМПП федеративного домена, с которым вы хотите разрешить пользователям добавлять контакты и взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="950bc-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="950bc-111">После того как политики будут установлены, необходимо настроить сертификаты шлюза КСМПП.</span><span class="sxs-lookup"><span data-stu-id="950bc-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="950bc-112">Функции КСМПП не рекомендуются в Skype для бизнеса Server 2019, но их можно продолжать использовать на устаревшем сервере в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="950bc-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="950bc-113">Убедитесь в том, что вы уже развернули старый сервер (Skype для бизнеса Server 2015/Lync Server 2013) КСМПП Gateway и настроили политики доступа, чтобы разрешить пользователям устаревших шлюзов КСМПП.</span><span class="sxs-lookup"><span data-stu-id="950bc-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="950bc-114">Подробности можно найти в разделе [Миграция Федерации КСМПП](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="950bc-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="950bc-115">Настройка политики внешнего доступа для предоставления пользователям устаревшего шлюза КСМПП</span><span class="sxs-lookup"><span data-stu-id="950bc-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="950bc-116">Откройте стандартную панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="950bc-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="950bc-117">На панели навигации слева выберите пункт **интеграция и внешний доступ**, а затем — **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="950bc-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="950bc-118">Нажмите кнопку **Создать** и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="950bc-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="950bc-119">Введите имя для политики пользователей внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="950bc-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="950bc-120">Введите описание для политики пользователей внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="950bc-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="950bc-121">Выберите **включить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="950bc-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="950bc-122">Выберите **включить связь с федеративными пользователями КСМПП**.</span><span class="sxs-lookup"><span data-stu-id="950bc-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="950bc-123">Нажмите \*\*\*\* кнопку Сохранить, чтобы сохранить изменения в политике сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="950bc-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

