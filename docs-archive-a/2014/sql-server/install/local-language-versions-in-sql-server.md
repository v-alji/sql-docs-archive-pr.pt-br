---
title: Versões de idiomas locais no SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 20b99363-0490-4aa3-9a3d-262f827d81e8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646ffaed1e4b709c2c26030379f0a7f223f221e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679634"
---
# <a name="local-language-versions-in-sql-server"></a><span data-ttu-id="05c45-102">Versões de idiomas locais no SQL Server</span><span class="sxs-lookup"><span data-stu-id="05c45-102">Local Language Versions in SQL Server</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="05c45-103">dá suporte a todos os idiomas que têm suporte nos sistemas operacionais Windows.</span><span class="sxs-lookup"><span data-stu-id="05c45-103">supports all languages that are supported by Windows operating systems.</span></span>  
  
## <a name="cross-language-support"></a><span data-ttu-id="05c45-104">Suporte entre idiomas</span><span class="sxs-lookup"><span data-stu-id="05c45-104">Cross-Language Support</span></span>  
  
-   <span data-ttu-id="05c45-105">Há suporte à versão no idioma inglês do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em todas as versões localizadas de sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="05c45-105">The English-language version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is supported on all localized versions of operating systems.</span></span>  
  
-   <span data-ttu-id="05c45-106">Também é dado suporte às versões localizadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em sistemas operacionais localizados com o idioma correspondente ou em versões em inglês de sistemas operacionais com suporte, usando as configurações do Windows MUI (Multilingual User Interface Pack).</span><span class="sxs-lookup"><span data-stu-id="05c45-106">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on localized operating systems with the corresponding language or on English-language versions of supported operating systems by using the Windows Multilingual User Interface Pack (MUI) settings.</span></span> <span data-ttu-id="05c45-107">Para obter mais informações, consulte [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span><span class="sxs-lookup"><span data-stu-id="05c45-107">For more information, see [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span></span>  
  
-   <span data-ttu-id="05c45-108">As versões localizadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] somente podem ser atualizadas para versões localizadas do mesmo idioma e não podem ser atualizadas para a versão em inglês.</span><span class="sxs-lookup"><span data-stu-id="05c45-108">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can only be upgraded to localized versions of the same language, and cannot be upgraded to the English-language version.</span></span>  
  
-   <span data-ttu-id="05c45-109">As versões localizadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] também podem ser instaladas lado a lado com instâncias em inglês do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c45-109">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can also be installed side by side with English-language instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="configure-operating-system-to-support-localized-versions"></a><a name="BK_ConfigureOS"></a> <span data-ttu-id="05c45-110">Configure Operating System to Support Localized Versions</span><span class="sxs-lookup"><span data-stu-id="05c45-110">Configure Operating System to Support Localized Versions</span></span>  
 <span data-ttu-id="05c45-111">As versões localizadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] têm suporte em versões no idioma inglês de sistemas operacionais com suporte; isso ocorre com o uso de configurações MUI Pack (Multilingual User Interface Pack) do Windows.</span><span class="sxs-lookup"><span data-stu-id="05c45-111">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on English-language versions of supported operating systems through the use of Windows Multilingual User Interface Pack (MUI) settings.</span></span>  
  
 <span data-ttu-id="05c45-112">Entretanto, você deve verificar determinadas configurações do sistema operacional antes de instalar uma versão localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um servidor que esteja executando um sistema operacional no idioma inglês com uma configuração de MUI não inglês.</span><span class="sxs-lookup"><span data-stu-id="05c45-112">However, you must verify certain operating system settings before installing a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a server that is running an English-language operating system with a non-English MUI setting.</span></span> <span data-ttu-id="05c45-113">Você precisa verificar se as seguintes configurações do sistema operacional correspondem ao idioma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] localizado a ser instalado:</span><span class="sxs-lookup"><span data-stu-id="05c45-113">You need to verify that the following operating system settings match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed:</span></span>  
  
-   <span data-ttu-id="05c45-114">A configuração de interface do usuário do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="05c45-114">The operating system user interface setting</span></span>  
  
-   <span data-ttu-id="05c45-115">A configuração de localidade do usuário do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="05c45-115">The operating system user locale setting</span></span>  
  
-   <span data-ttu-id="05c45-116">A configuração de localidade do sistema</span><span class="sxs-lookup"><span data-stu-id="05c45-116">The system locale setting</span></span>  
  
 <span data-ttu-id="05c45-117">Se as configurações não corresponderem ao idioma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] localizado a ser instalado, use os procedimentos a seguir para definir corretamente essas configurações do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="05c45-117">If the settings do not match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed, then use the following procedures to correctly set these operating system settings.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="05c45-118">Não há suporte para instalações de versões de idioma diferentes de instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="05c45-118">Installations of different language versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances on the same computer are not supported.</span></span>  
  
#### <a name="to-change-the-operating-system-user-interface-setting"></a><span data-ttu-id="05c45-119">Para alterar a configuração da interface do usuário do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="05c45-119">To change the operating system user interface setting</span></span>  
  
1.  <span data-ttu-id="05c45-120">Se ainda não estiver instalado, instale o MUI do sistema operacional que corresponde à sua versão localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c45-120">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="05c45-121">No Painel de Controle, abra **Opções Regionais e de Idioma**.</span><span class="sxs-lookup"><span data-stu-id="05c45-121">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="05c45-122">Na guia **Idiomas** , para **Idioma usado em menus e caixas de diálogo**, selecione um valor da lista.</span><span class="sxs-lookup"><span data-stu-id="05c45-122">On the **Languages** tab, for **Language used in menus and dialogs**, select a value from the list.</span></span>  
  
     <span data-ttu-id="05c45-123">Essa configuração afetará o idioma da interface do usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], portanto deve corresponder à sua versão localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c45-123">This setting will affect the user interface language of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so it must match your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="05c45-124">Clique em **Aplicar** para confirmar a alteração e em **OK** para fechar a janela.</span><span class="sxs-lookup"><span data-stu-id="05c45-124">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-operating-system-user-locale-setting"></a><span data-ttu-id="05c45-125">Para alterar a configuração da localidade do usuário do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="05c45-125">To change the operating system user locale setting</span></span>  
  
1.  <span data-ttu-id="05c45-126">Se ainda não estiver instalado, instale o MUI do sistema operacional que corresponde à sua versão localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c45-126">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="05c45-127">No Painel de Controle, abra **Opções Regionais e de Idioma**.</span><span class="sxs-lookup"><span data-stu-id="05c45-127">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="05c45-128">Na guia **Opções Regionais** , para **Selecione um item correspondente às suas preferências**, selecione um valor da lista.</span><span class="sxs-lookup"><span data-stu-id="05c45-128">On the **Regional Options** tab, for **Select an item to match its preferences**, select a value from the list.</span></span>  
  
     <span data-ttu-id="05c45-129">Essa configuração afetará a formatação de dados específicos da cultura.</span><span class="sxs-lookup"><span data-stu-id="05c45-129">This setting will affect culture-specific data formatting.</span></span>  
  
4.  <span data-ttu-id="05c45-130">Clique em **Aplicar** para confirmar a alteração e em **OK** para fechar a janela.</span><span class="sxs-lookup"><span data-stu-id="05c45-130">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-system-locale-setting"></a><span data-ttu-id="05c45-131">Par alterar a configuração de localidade do sistema</span><span class="sxs-lookup"><span data-stu-id="05c45-131">To change the system locale setting</span></span>  
  
1.  <span data-ttu-id="05c45-132">Se ainda não estiver instalado, instale o MUI do sistema operacional que corresponde à sua versão localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c45-132">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="05c45-133">No Painel de Controle, abra **Opções Regionais e de Idioma**.</span><span class="sxs-lookup"><span data-stu-id="05c45-133">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="05c45-134">Na guia **Avançado** , para **Select a language to match the language version of the non-Unicode programs you want to use (Selecione um idioma correspondente à versão de idioma dos programas não Unicode que você deseja usar)** , selecione um valor da lista.</span><span class="sxs-lookup"><span data-stu-id="05c45-134">On the **Advanced** tab, for **Select a language to match the language version of the non-Unicode programs you want to use**, select a value from the list.</span></span>  
  
     <span data-ttu-id="05c45-135">Essa configuração permitirá que a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escolha a melhor ordenação padrão para sua instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c45-135">This setting will allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to choose the best default collation for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
4.  <span data-ttu-id="05c45-136">Clique em **Aplicar** para confirmar a alteração e em **OK** para fechar a janela.</span><span class="sxs-lookup"><span data-stu-id="05c45-136">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c45-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05c45-137">See Also</span></span>  
 <span data-ttu-id="05c45-138">[Requisitos de hardware e software para a instalação do SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="05c45-138">[Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 [<span data-ttu-id="05c45-139">Instalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="05c45-139">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
