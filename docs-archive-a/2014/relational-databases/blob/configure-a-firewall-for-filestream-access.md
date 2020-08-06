---
title: Configurar um firewall para acesso ao FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- Windows Firewall [Database Engine], FILESTREAM
- FILESTREAM [SQL Server], Windows Firewall
ms.assetid: fc52007f-c26f-4f8e-b9d8-55a7978f4d56
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8b787403fefdd336dd82bf7ccb93cdf21fe5a90d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581971"
---
# <a name="configure-a-firewall-for-filestream-access"></a><span data-ttu-id="067cb-102">Configurar um firewall para acesso ao FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="067cb-102">Configure a Firewall for FILESTREAM Access</span></span>
  <span data-ttu-id="067cb-103">Para usar FILESTREAM em um ambiente protegido por firewall, o cliente e o servidor devem poder resolver nomes DNS para o servidor que contém os arquivos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="067cb-103">To use FILESTREAM in a firewall-protected environment, both the client and server must be able to resolve DNS names to the server that contains the FILESTREAM files.</span></span> <span data-ttu-id="067cb-104">O FILESTREAM exige que as portas de compartilhamento de arquivos do Windows 139 e 445 estejam abertas.</span><span class="sxs-lookup"><span data-stu-id="067cb-104">FILESTREAM requires the Windows file-sharing ports 139 and 445 to be open.</span></span>  
  
### <a name="to-open-the-windows-file-sharing-ports-on-a-computer-that-is-running-windows-7"></a><span data-ttu-id="067cb-105">Para abrir as portas de compartilhamento de arquivos do Windows em um computador que está executando o Windows 7</span><span class="sxs-lookup"><span data-stu-id="067cb-105">To open the Windows file-sharing ports on a computer that is running Windows 7</span></span>  
  
1.  <span data-ttu-id="067cb-106">No Painel de Controle, abra o **Firewall do Windows**.</span><span class="sxs-lookup"><span data-stu-id="067cb-106">In Control Panel, open **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="067cb-107">No painel esquerdo, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="067cb-107">In the left pane, click **Advanced settings**.</span></span> <span data-ttu-id="067cb-108">Se você for solicitado para uma senha de administrador ou confirmação, digite a senha ou forneça a confirmação.</span><span class="sxs-lookup"><span data-stu-id="067cb-108">If you're prompted for an administrator password or confirmation, type the password or provide confirmation.</span></span>  
  
3.  <span data-ttu-id="067cb-109">Na caixa de diálogo **Firewall do Windows com Segurança Avançada** , no painel esquerdo, clique em **Regras de Entrada**e, no painel direito, clique em **Nova Regra**.</span><span class="sxs-lookup"><span data-stu-id="067cb-109">In the **Windows Firewall with Advanced Security** dialog box, in the left pane, click **Inbound Rules**, and then, in the right pane, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="067cb-110">Siga as instruções do assistente Nova Regra de Entrada para adicionar a porta TCP 139.</span><span class="sxs-lookup"><span data-stu-id="067cb-110">Follow the instructions in the New Inbound Rule wizard to add TCP port 139.</span></span>  
  
5.  <span data-ttu-id="067cb-111">Repita a etapa anterior para adicionar a porta TCP 445.</span><span class="sxs-lookup"><span data-stu-id="067cb-111">Repeat the previous step to add TCP port 445.</span></span>  
  
6.  <span data-ttu-id="067cb-112">Feche a caixa de diálogo **Firewall do Windows com Segurança Avançada** .</span><span class="sxs-lookup"><span data-stu-id="067cb-112">Close the **Windows Firewall with Advanced Security** dialog box.</span></span>  
  
  
