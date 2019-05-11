---
title: Процесс развертывания для объявлений приложения в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Процесс развертывания и действия для объявлений приложения в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 27e22c95e58ac84fa3f27aef8b2d18cb1b1226dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892561"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="fffd3-103">Процесс развертывания для объявлений приложения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="fffd3-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="fffd3-104">Процесс развертывания и действия для объявлений приложения в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fffd3-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fffd3-105">Объявление приложения — это функция корпоративной голосовой связи, которая позволяет настроить, что происходит с вызовы неназначенных extensions (расширения, которые являются допустимыми для вашей организации, но не назначенные человека или телефон).</span><span class="sxs-lookup"><span data-stu-id="fffd3-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="fffd3-106">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="fffd3-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="fffd3-107">Приложение оповещения устанавливается как компонент приложения группы ответа на сервере переднего плана или сервере Standard Edition, при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fffd3-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fffd3-108">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="fffd3-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="fffd3-109">В этом разделе Обзор действий, необходимых для развертывания приложения объявлений.</span><span class="sxs-lookup"><span data-stu-id="fffd3-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="fffd3-110">Перед настройкой извещения, необходимо развернуть корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fffd3-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="fffd3-111">Компоненты, необходимые для объявлений приложения установлены и включены при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fffd3-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="fffd3-112">**Процесс развертывания объявлений**</span><span class="sxs-lookup"><span data-stu-id="fffd3-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="fffd3-113">**Этап**</span><span class="sxs-lookup"><span data-stu-id="fffd3-113">**Phase**</span></span>|<span data-ttu-id="fffd3-114">**Шаги**</span><span class="sxs-lookup"><span data-stu-id="fffd3-114">**Steps**</span></span>|<span data-ttu-id="fffd3-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="fffd3-115">**Roles**</span></span>|<span data-ttu-id="fffd3-116">**Документация по развертыванию**</span><span class="sxs-lookup"><span data-stu-id="fffd3-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fffd3-117">Настройка параметров объявлений</span><span class="sxs-lookup"><span data-stu-id="fffd3-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="fffd3-118">Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</span><span class="sxs-lookup"><span data-stu-id="fffd3-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="fffd3-119">Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</span><span class="sxs-lookup"><span data-stu-id="fffd3-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="fffd3-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="fffd3-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="fffd3-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="fffd3-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="fffd3-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="fffd3-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="fffd3-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="fffd3-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="fffd3-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="fffd3-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="fffd3-125">Создание и удаление оповещения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="fffd3-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="fffd3-126">Создание или изменение диапазона неназначенных номеров в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="fffd3-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="fffd3-127">Проверка развертывания объявления</span><span class="sxs-lookup"><span data-stu-id="fffd3-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="fffd3-128">Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</span><span class="sxs-lookup"><span data-stu-id="fffd3-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="fffd3-129">(Необязательно) Проверка развертывания объявлений в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fffd3-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

