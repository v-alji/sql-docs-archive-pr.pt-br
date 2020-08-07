---
title: Representação e credenciais para conexões | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- impersonation [CLR integration]
- security [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- authentication [CLR integration]
- user impersonation [CLR integration]
- credentials [CLR integration]
- database objects [CLR integration], security
ms.assetid: 293dce7d-1db2-4657-992f-8c583d6e9ebb
author: rothja
ms.author: jroth
ms.openlocfilehash: cdbc52e07f4502adda7301ce7f635c050ed9c3c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575166"
---
# <a name="impersonation-and-credentials-for-connections"></a><span data-ttu-id="32864-102">Representação e credenciais para conexões</span><span class="sxs-lookup"><span data-stu-id="32864-102">Impersonation and Credentials for Connections</span></span>
  <span data-ttu-id="32864-103">Na integração CLR (Common Language Runtime) do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o uso da Autenticação do Windows é complexo, porém é mais seguro do que o uso da Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32864-103">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] common language runtime (CLR) integration, using Windows Authentication is complex, but is more secure than using SQL Server Authentication.</span></span> <span data-ttu-id="32864-104">Quando usar a Autenticação do Windows, lembre-se das considerações a seguir.</span><span class="sxs-lookup"><span data-stu-id="32864-104">When using Windows Authentication, keep in mind the following considerations.</span></span>  
  
 <span data-ttu-id="32864-105">Por padrão, um processo do SQL Server que se conecta ao Windows adquire o contexto de segurança da conta de serviço do Windows para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32864-105">By default, a SQL Server process that connects out to Windows acquires the security context of the SQL Server Windows service account.</span></span> <span data-ttu-id="32864-106">Todavia, é possível mapear uma função CLR para uma identidade proxy, de modo que suas conexões de saída tenham um contexto de segurança diferente daquele da conta de serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="32864-106">But it is possible to map a CLR function to a proxy identity, so that its outbound connections have a different security context than that of the Windows service account.</span></span>  
  
 <span data-ttu-id="32864-107">Em alguns casos, talvez você queira representar o chamador usando a propriedade `SqlContext.WindowsIdentity` em vez de executar como a conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="32864-107">In some cases, you may want to impersonate the caller by using the `SqlContext.WindowsIdentity` property instead of running as the service account.</span></span> <span data-ttu-id="32864-108">A instância de `WindowsIdentity` representa a identidade do cliente que invocou o código de chamada e só estará disponível se o cliente usou a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="32864-108">The `WindowsIdentity` instance represents the identity of the client that invoked the calling code, and is only available when the client used Windows Authentication.</span></span> <span data-ttu-id="32864-109">Depois de obter a instância de `WindowsIdentity`, você poderá chamar `Impersonate` para alterar o token de segurança do thread e, em seguida, abrir as conexões ADO.NET em nome do cliente.</span><span class="sxs-lookup"><span data-stu-id="32864-109">After you have obtained the `WindowsIdentity` instance, you can call `Impersonate` to change the security token of the thread, and then open ADO.NET connections on behalf of the client.</span></span>  
  
 <span data-ttu-id="32864-110">Depois de chamar SQLContext. WindowsIdentity. Impersonate, você não pode acessar dados locais e não pode acessar os dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="32864-110">After you call SQLContext.WindowsIdentity.Impersonate, you cannot access local data and you cannot access system data.</span></span> <span data-ttu-id="32864-111">Para acessar dados novamente, você precisa chamar WindowsImpersonationContext. Undo.</span><span class="sxs-lookup"><span data-stu-id="32864-111">To access data again, you have to call WindowsImpersonationContext.Undo.</span></span>  
  
 <span data-ttu-id="32864-112">O exemplo a seguir mostra como representar o chamador por meio da propriedade `SqlContext.WindowsIdentity`.</span><span class="sxs-lookup"><span data-stu-id="32864-112">The following example shows how to impersonate the caller by using the `SqlContext.WindowsIdentity` property.</span></span>  
  
 <span data-ttu-id="32864-113">Visual C#</span><span class="sxs-lookup"><span data-stu-id="32864-113">Visual C#</span></span>  
  
```  
WindowsIdentity clientId = null;  
WindowsImpersonationContext impersonatedUser = null;  
  
clientId = SqlContext.WindowsIdentity;  
  
// This outer try block is used to protect from   
// exception filter attacks which would prevent  
// the inner finally block from executing and   
// resetting the impersonation.  
try  
{  
   try  
   {  
      impersonatedUser = clientId.Impersonate();  
      if (impersonatedUser != null)  
         return GetFileDetails(directoryPath);  
         else return null;  
   }  
   finally  
   {  
      if (impersonatedUser != null)  
         impersonatedUser.Undo();  
   }  
}  
catch  
{  
   throw;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="32864-114">Para obter informações sobre alterações de comportamento na representação, consulte [alterações recentes em mecanismo de banco de dados recursos no SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="32864-114">For information about behavior changes in impersonation, see [Breaking Changes to Database Engine Features in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="32864-115">Além disso, se você obteve a instância de identidade do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows, por padrão não poderá propagar essa instância para outro computador; a infraestrutura de segurança do Windows impõe essa restrição por padrão.</span><span class="sxs-lookup"><span data-stu-id="32864-115">Furthermore, if you obtained the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows identity instance, by default you cannot propagate that instance to another computer; Windows security infrastructure restricts that by default.</span></span> <span data-ttu-id="32864-116">Porém, há um mecanismo chamado "delegação" que permite a propagação de identidades do Windows por vários computadores.</span><span class="sxs-lookup"><span data-stu-id="32864-116">There is, however, a mechanism called "delegation" that enables propagation of Windows identities across multiple trusted computers.</span></span> <span data-ttu-id="32864-117">Você pode saber mais sobre a delegação no artigo do TechNet, "[transição de protocolo Kerberos e delegação restrita](https://go.microsoft.com/fwlink/?LinkId=50419)".</span><span class="sxs-lookup"><span data-stu-id="32864-117">You can learn more about delegation in the TechNet article, "[Kerberos Protocol Transition and Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=50419)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32864-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32864-118">See Also</span></span>  
 [<span data-ttu-id="32864-119">Objeto SqlContext</span><span class="sxs-lookup"><span data-stu-id="32864-119">SqlContext Object</span></span>](../../clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
  
  
