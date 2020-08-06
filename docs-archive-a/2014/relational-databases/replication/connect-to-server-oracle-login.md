---
title: Conectar ao Servidor (Oracle), Logon | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.login.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 86ed91a1-a07c-46f2-a913-67317ef2255e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23f5b515fcb1e80416d860e2ff3a2e6be5431819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569376"
---
# <a name="connect-to-server-oracle-login"></a><span data-ttu-id="4f8c6-102">Conectar ao Servidor (Oracle), Logon</span><span class="sxs-lookup"><span data-stu-id="4f8c6-102">Connect to Server (Oracle), Login</span></span>
  <span data-ttu-id="4f8c6-103">Use a guia **Logon** da caixa de diálogo **Conectar ao Servidor** para especificar a conta na qual as conexões são feitas do Distribuidor do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o Publicador Oracle.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-103">Use the **Login** tab of the **Connect to Server** dialog box to specify the account under which connections are made from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor to the Oracle Publisher.</span></span> <span data-ttu-id="4f8c6-104">Você deve usar a mesma conta especificada para o esquema de usuário administrativo de replicação durante a configuração do Publicador.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-104">You must use the same account as the one specified for the replication administrative user schema during configuration of the Publisher.</span></span> <span data-ttu-id="4f8c6-105">Para obter mais informações, consulte [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md) (Configurar um publicador do Oracle).</span><span class="sxs-lookup"><span data-stu-id="4f8c6-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4f8c6-106">Opções</span><span class="sxs-lookup"><span data-stu-id="4f8c6-106">Options</span></span>  
 <span data-ttu-id="4f8c6-107">**Instância de servidor**</span><span class="sxs-lookup"><span data-stu-id="4f8c6-107">**Server instance**</span></span>  
 <span data-ttu-id="4f8c6-108">O nome TNS (Transparent Network Substrate) do Editor Oracle, especificado durante a configuração do software cliente Oracle instalado no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-108">The Transparent Network Substrate (TNS) name of the Oracle Publisher, which is specified during configuration of the Oracle client software installed on the Distributor.</span></span>  
  
 <span data-ttu-id="4f8c6-109">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="4f8c6-109">**Authentication**</span></span>  
 <span data-ttu-id="4f8c6-110">Selecione **Autenticação Padrão da Oracle** (recomendado) ou **Autenticação do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-110">Select **Oracle Standard Authentication** (recommended) or **Windows Authentication**.</span></span> <span data-ttu-id="4f8c6-111">Se você selecionar **Autenticação do Windows**:</span><span class="sxs-lookup"><span data-stu-id="4f8c6-111">If you select **Windows Authentication**:</span></span>  
  
-   <span data-ttu-id="4f8c6-112">O servidor Oracle deve ser configurado para permitir conexões que usam credenciais do Windows.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-112">The Oracle server must be configured to allow connections using Windows credentials.</span></span> <span data-ttu-id="4f8c6-113">Para obter mais informações, consulte a documentação Oracle.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-113">For more information, see the Oracle documentation.</span></span>  
  
-   <span data-ttu-id="4f8c6-114">Você deve estar registrado atualmente na mesma conta [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows especificada para o esquema de usuário administrativo de replicação.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-114">You must be currently logged in with the same [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account you specified for the replication administrative user schema.</span></span>  
  
 <span data-ttu-id="4f8c6-115">**Logon** e **Senha**</span><span class="sxs-lookup"><span data-stu-id="4f8c6-115">**Login** and **Password**</span></span>  
 <span data-ttu-id="4f8c6-116">Se você tiver selecionado **Autenticação Padrão da Oracle** para a opção **Autenticação** , especifique o logon e a senha a serem usados, que devem ser os mesmos que os especificados para o esquema de usuário administrativo de replicação.</span><span class="sxs-lookup"><span data-stu-id="4f8c6-116">If you selected **Oracle Standard Authentication** for the **Authentication** option, specify the login and password to use, which must be the same as those specified for the replication administrative user schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8c6-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f8c6-117">See Also</span></span>  
 [<span data-ttu-id="4f8c6-118">Glossário de termos para publicações Oracle</span><span class="sxs-lookup"><span data-stu-id="4f8c6-118">Glossary of Terms for Oracle Publishing</span></span>](non-sql/glossary-of-terms-for-oracle-publishing.md)  
  
  
