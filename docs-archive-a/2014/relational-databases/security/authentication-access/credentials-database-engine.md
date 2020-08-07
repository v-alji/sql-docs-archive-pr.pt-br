---
title: Credenciais (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- principals [SQL Server], credentials
- schemas [SQL Server], credentials
- permissions [SQL Server], credentials
- groups [SQL Server], credentials
- ALTER ANY CREDENTIAL permission
- security [SQL Server], credentials
- authentication [SQL Server], credentials
- users [SQL Server], credentials
- credentials [SQL Server], about credentials
- credentials [SQL Server]
ms.assetid: c8df6022-e0b4-46b8-9670-3f86938d3177
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: faa2b5be7cf6918b5d5232763a96ed4dbbc89e51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581724"
---
# <a name="credentials-database-engine"></a><span data-ttu-id="4c8f9-102">Credenciais (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="4c8f9-102">Credentials (Database Engine)</span></span>
  <span data-ttu-id="4c8f9-103">Uma credencial é um registro que contém as informações de autenticação(credenciais) necessárias para conectar-se a um recurso fora do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c8f9-103">A credential is a record that contains the authentication information (credentials) required to connect to a resource outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4c8f9-104">Essas informações são usadas internamente pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c8f9-104">This information is used internally by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4c8f9-105">A maioria das credenciais contém um nome e uma senha de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="4c8f9-105">Most credentials contain a Windows user name and password.</span></span>  
  
 <span data-ttu-id="4c8f9-106">As informações armazenadas em uma credencial permite que um usuário quem se conectou com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] por meio da Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] acesse os recursos fora da instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="4c8f9-106">The information stored in a credential enables a user who has connected to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by way of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to access resources outside the server instance.</span></span> <span data-ttu-id="4c8f9-107">Quando o recurso externo for o Windows, o usuário é autenticado como o usuário de Windows especificado na credencial.</span><span class="sxs-lookup"><span data-stu-id="4c8f9-107">When the external resource is Windows, the user is authenticated as the Windows user specified in the credential.</span></span> <span data-ttu-id="4c8f9-108">Uma única credencial pode ser mapeada para vários logons do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c8f9-108">A single credential can be mapped to multiple [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="4c8f9-109">No entanto, um logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] só pode ser mapeado para uma credencial.</span><span class="sxs-lookup"><span data-stu-id="4c8f9-109">However, a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can be mapped to only one credential.</span></span>  
  
 <span data-ttu-id="4c8f9-110">Credenciais de sistema são criadas automaticamente e associadas a pontos de extremidade específicos.</span><span class="sxs-lookup"><span data-stu-id="4c8f9-110">System credentials are created automatically and are associated with specific endpoints.</span></span> <span data-ttu-id="4c8f9-111">Nomes para credenciais de sistema iniciam com dois sinais de hash (##).</span><span class="sxs-lookup"><span data-stu-id="4c8f9-111">Names for system credentials start with two hash signs (##).</span></span>  
  
 <span data-ttu-id="4c8f9-112">Para obter mais informações sobre credenciais, consulte a exibição do catálogo [Sys. Credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4c8f9-112">For more information about credentials, see the [sys.credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) catalog view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4c8f9-113">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="4c8f9-113">Related Content</span></span>  
 <span data-ttu-id="4c8f9-114">[Criar uma](../authentication-access/create-a-credential.md) credencial criar credencial [&#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="4c8f9-114">[Create a Credential](../authentication-access/create-a-credential.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span></span>  
  
 [<span data-ttu-id="4c8f9-115">Protegendo o SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c8f9-115">Securing SQL Server</span></span>](../securing-sql-server.md)  
  
  
