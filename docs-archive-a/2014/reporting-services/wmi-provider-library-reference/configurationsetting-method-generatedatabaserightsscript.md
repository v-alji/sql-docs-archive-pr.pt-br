---
title: Método GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseRightsScript method
ms.assetid: f2e6dcc9-978f-4c2c-bafe-36c330247fd0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 768e73d13d3b06f7913c3c816fded1b28c56199f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684009"
---
# <a name="generatedatabaserightsscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="15a0c-102">Método GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="15a0c-102">GenerateDatabaseRightsScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="15a0c-103">Gera um Script SQL que pode ser usado para conceder direitos de usuário ao banco de dados do servidor de relatório e a outros bancos de dados necessários para a execução de um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="15a0c-103">Generates a SQL Script that can be used to grant a user rights to the report server database and other databases required for a report server to run.</span></span> <span data-ttu-id="15a0c-104">O chamador deve se conectar ao servidor de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e executar o script.</span><span class="sxs-lookup"><span data-stu-id="15a0c-104">The caller is expected to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and execute the script.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a0c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="15a0c-105">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseRightsScript(ByVal UserName As String, _  
    ByVal DatabaseName As String, ByVal IsRemote As Boolean, _  
    ByVal IsWindowsUser As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseRightsScript(string UserName, string DatabaseName, bool IsRemote, bool IsWindowsUser, out string Script,   
out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15a0c-106">parâmetros</span><span class="sxs-lookup"><span data-stu-id="15a0c-106">Parameters</span></span>  
 <span data-ttu-id="15a0c-107">*UserName*</span><span class="sxs-lookup"><span data-stu-id="15a0c-107">*UserName*</span></span>  
 <span data-ttu-id="15a0c-108">O nome de usuário ou o identificador de segurança (SID) do Windows do usuário ao qual o script concederá direitos.</span><span class="sxs-lookup"><span data-stu-id="15a0c-108">The user name or Windows security identifier (SID) of the user to which the script will grant rights.</span></span>  
  
 <span data-ttu-id="15a0c-109">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="15a0c-109">*DatabaseName*</span></span>  
 <span data-ttu-id="15a0c-110">O nome do banco de dados para o qual o script concederá acesso ao usuário.</span><span class="sxs-lookup"><span data-stu-id="15a0c-110">The database name to which the script will grant access to the user.</span></span>  
  
 <span data-ttu-id="15a0c-111">*IsRemote*</span><span class="sxs-lookup"><span data-stu-id="15a0c-111">*IsRemote*</span></span>  
 <span data-ttu-id="15a0c-112">Um valor Booleano que indica se o banco de dados é remoto em relação ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="15a0c-112">A Boolean value to indicating whether the database is remote from the report server.</span></span>  
  
 <span data-ttu-id="15a0c-113">*IsWindowsUser*</span><span class="sxs-lookup"><span data-stu-id="15a0c-113">*IsWindowsUser*</span></span>  
 <span data-ttu-id="15a0c-114">Um valor Booleano que indica se o nome de usuário especificado é de um usuário do Windows ou de um usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15a0c-114">A Boolean value indicating whether the specified user name is a Windows user or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="15a0c-115">*Script*</span><span class="sxs-lookup"><span data-stu-id="15a0c-115">*Script*</span></span>  
 <span data-ttu-id="15a0c-116">[out] Uma cadeia de caracteres que contém o script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gerado.</span><span class="sxs-lookup"><span data-stu-id="15a0c-116">[out] A string containing the generated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span>  
  
 <span data-ttu-id="15a0c-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="15a0c-117">*HRESULT*</span></span>  
 <span data-ttu-id="15a0c-118">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="15a0c-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15a0c-119">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="15a0c-119">Return Value</span></span>  
 <span data-ttu-id="15a0c-120">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="15a0c-120">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="15a0c-121">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="15a0c-121">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="15a0c-122">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="15a0c-122">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15a0c-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="15a0c-123">Remarks</span></span>  
 <span data-ttu-id="15a0c-124">Se *DatabaseName* ficar vazio, *IsRemote* será ignorado e o valor do arquivo de configuração do servidor de relatório será usado como o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="15a0c-124">If *DatabaseName* is empty then *IsRemote* is ignored and the report server configuration file value is used for the database name.</span></span>  
  
 <span data-ttu-id="15a0c-125">Se *IsWindowsUser* for definido como `true` , *username* deverá estar no formato \<domain> \\<nome de usuário \> .</span><span class="sxs-lookup"><span data-stu-id="15a0c-125">If *IsWindowsUser* is set to `true`, *UserName* should be in the format \<domain>\\<username\>.</span></span>  
  
 <span data-ttu-id="15a0c-126">Quando *IsWindowsUser* é definido como `true` , o script gerado concede direitos de logon ao usuário para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , definindo o banco de dados do servidor de relatório como o banco de dados padrão e concede a função **RSExec** no banco de dados do servidor de relatório, o banco de dados temporário do servidor de relatório, o banco de dados mestre e o banco de dados do sistema msdb.</span><span class="sxs-lookup"><span data-stu-id="15a0c-126">When *IsWindowsUser* is set to `true`, the generated script grants login rights to the user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], setting the report server database as the default database, and grants the **RSExec** role on the report server database, the report server temporary database, the master database and the MSDB system database.</span></span>  
  
 <span data-ttu-id="15a0c-127">Quando *IsWindowsUser* é definido como `true` , o método aceita os SIDs do Windows padrão como entrada.</span><span class="sxs-lookup"><span data-stu-id="15a0c-127">When *IsWindowsUser* is set to `true`, the method accepts standard Windows SIDs as input.</span></span> <span data-ttu-id="15a0c-128">Quando um SID do Windows padrão ou nome de conta de serviço é fornecido, ele é convertido em uma cadeia de caracteres de nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="15a0c-128">When a standard Windows SID or service account name is supplied, it is translated to a user name string.</span></span> <span data-ttu-id="15a0c-129">Se o banco de dados for local, a conta será convertida para a representação localizada correta da conta.</span><span class="sxs-lookup"><span data-stu-id="15a0c-129">If the database is local, the account is translated to the correct localized representation of the account.</span></span> <span data-ttu-id="15a0c-130">Se o banco de dados for remoto, a conta será representada como a conta do computador.</span><span class="sxs-lookup"><span data-stu-id="15a0c-130">If the database is remote, the account is represented as the computer's account.</span></span>  
  
 <span data-ttu-id="15a0c-131">A tabela a seguir mostra as contas que são convertidas e sua representação remota.</span><span class="sxs-lookup"><span data-stu-id="15a0c-131">The following table shows accounts that are translated and their remote representation.</span></span>  
  
|<span data-ttu-id="15a0c-132">Conta/SID que está convertido</span><span class="sxs-lookup"><span data-stu-id="15a0c-132">Account / SID that is translated</span></span>|<span data-ttu-id="15a0c-133">Nome comum</span><span class="sxs-lookup"><span data-stu-id="15a0c-133">Common Name</span></span>|<span data-ttu-id="15a0c-134">Nome remoto</span><span class="sxs-lookup"><span data-stu-id="15a0c-134">Remote Name</span></span>|  
|---------------------------------------|-----------------|-----------------|  
|<span data-ttu-id="15a0c-135">(S-1-5-18)</span><span class="sxs-lookup"><span data-stu-id="15a0c-135">(S-1-5-18)</span></span>|<span data-ttu-id="15a0c-136">Sistema Local</span><span class="sxs-lookup"><span data-stu-id="15a0c-136">Local System</span></span>|<span data-ttu-id="15a0c-137">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="15a0c-137">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="15a0c-138">.\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="15a0c-138">.\LocalSystem</span></span>|<span data-ttu-id="15a0c-139">Sistema Local</span><span class="sxs-lookup"><span data-stu-id="15a0c-139">Local System</span></span>|<span data-ttu-id="15a0c-140">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="15a0c-140">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="15a0c-141">Nome do computador\sistema local</span><span class="sxs-lookup"><span data-stu-id="15a0c-141">ComputerName\LocalSystem</span></span>|<span data-ttu-id="15a0c-142">Sistema Local</span><span class="sxs-lookup"><span data-stu-id="15a0c-142">Local System</span></span>|<span data-ttu-id="15a0c-143">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="15a0c-143">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="15a0c-144">LocalSystem</span><span class="sxs-lookup"><span data-stu-id="15a0c-144">LocalSystem</span></span>|<span data-ttu-id="15a0c-145">Sistema Local</span><span class="sxs-lookup"><span data-stu-id="15a0c-145">Local System</span></span>|<span data-ttu-id="15a0c-146">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="15a0c-146">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="15a0c-147">(S-1-5-20)</span><span class="sxs-lookup"><span data-stu-id="15a0c-147">(S-1-5-20)</span></span>|<span data-ttu-id="15a0c-148">Serviço de Rede</span><span class="sxs-lookup"><span data-stu-id="15a0c-148">Network Service</span></span>|<span data-ttu-id="15a0c-149">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="15a0c-149">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="15a0c-150">NT AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="15a0c-150">NT AUTHORITY\NetworkService</span></span>|<span data-ttu-id="15a0c-151">Serviço de Rede</span><span class="sxs-lookup"><span data-stu-id="15a0c-151">Network Service</span></span>|<span data-ttu-id="15a0c-152">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="15a0c-152">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="15a0c-153">(S-1-5-19)</span><span class="sxs-lookup"><span data-stu-id="15a0c-153">(S-1-5-19)</span></span>|<span data-ttu-id="15a0c-154">Serviço Local</span><span class="sxs-lookup"><span data-stu-id="15a0c-154">Local Service</span></span>|<span data-ttu-id="15a0c-155">Erro – veja abaixo.</span><span class="sxs-lookup"><span data-stu-id="15a0c-155">Error - see below.</span></span>|  
|<span data-ttu-id="15a0c-156">NT AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="15a0c-156">NT AUTHORITY\LocalService</span></span>|<span data-ttu-id="15a0c-157">Serviço Local</span><span class="sxs-lookup"><span data-stu-id="15a0c-157">Local Service</span></span>|<span data-ttu-id="15a0c-158">Erro – veja abaixo.</span><span class="sxs-lookup"><span data-stu-id="15a0c-158">Error - see below.</span></span>|  
  
 <span data-ttu-id="15a0c-159">No [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], se você estiver usando uma conta interna e o banco de dados do servidor de relatório for remoto, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="15a0c-159">On [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], if you are using a built-in account and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="15a0c-160">Se a conta interna `LocalService` for especificada e o banco de dados do servidor de relatório for remoto, um erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="15a0c-160">If the `LocalService` built-in account is specified and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="15a0c-161">Quando *IsWindowsUser* for true e o valor fornecido no *UserName* precisar ser convertido, o provedor WMI determinará se o banco de dados do servidor de relatório está localizado no mesmo computador ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="15a0c-161">When *IsWindowsUser* is true and the value supplied in *UserName* needs to be translated, the WMI provider determines whether the report server database is located on the same computer or on a remote computer.</span></span> <span data-ttu-id="15a0c-162">Para determinar se a instalação é local, o provedor de WMI avaliará a propriedade DatabaseServerName da lista de valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="15a0c-162">To determine if the installation is local, the WMI provider evaluates the DatabaseServerName property against the following list of values.</span></span> <span data-ttu-id="15a0c-163">Se uma correspondência for localizada, o banco de dados é local.</span><span class="sxs-lookup"><span data-stu-id="15a0c-163">If a match is found, the database is local.</span></span> <span data-ttu-id="15a0c-164">Caso contrário, é remoto.</span><span class="sxs-lookup"><span data-stu-id="15a0c-164">Otherwise, it is remote.</span></span> <span data-ttu-id="15a0c-165">A comparação não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="15a0c-165">The comparison is case-insensitive.</span></span>  
  
|<span data-ttu-id="15a0c-166">Valor do DatabaseServerName</span><span class="sxs-lookup"><span data-stu-id="15a0c-166">Value of DatabaseServerName</span></span>|<span data-ttu-id="15a0c-167">Exemplo</span><span class="sxs-lookup"><span data-stu-id="15a0c-167">Example</span></span>|  
|---------------------------------|-------------|  
|<span data-ttu-id="15a0c-168">"."</span><span class="sxs-lookup"><span data-stu-id="15a0c-168">"."</span></span>||  
|<span data-ttu-id="15a0c-169">"(local)"</span><span class="sxs-lookup"><span data-stu-id="15a0c-169">"(local)"</span></span>||  
|<span data-ttu-id="15a0c-170">"LOCAL"</span><span class="sxs-lookup"><span data-stu-id="15a0c-170">"LOCAL"</span></span>||  
|<span data-ttu-id="15a0c-171">localhost</span><span class="sxs-lookup"><span data-stu-id="15a0c-171">localhost</span></span>||  
|\<Machinename>|<span data-ttu-id="15a0c-172">testlab14</span><span class="sxs-lookup"><span data-stu-id="15a0c-172">testlab14</span></span>|  
|\<MachineFQDN>|<span data-ttu-id="15a0c-173">example.redmond.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="15a0c-173">example.redmond.microsoft.com</span></span>|  
|\<IPAddress>|<span data-ttu-id="15a0c-174">180.012.345,678</span><span class="sxs-lookup"><span data-stu-id="15a0c-174">180.012.345,678</span></span>|  
  
 <span data-ttu-id="15a0c-175">Quando *IsWindowsUser* é definido como `true` , o provedor WMI chama LookupAccountName para obter o SID da conta e, em seguida, chama LookupAccountSID para obter o nome a ser colocado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span><span class="sxs-lookup"><span data-stu-id="15a0c-175">When *IsWindowsUser* is set to `true`, the WMI provider calls LookupAccountName to get the SID for the account and then calls LookupAccountSID to get the name to put in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span> <span data-ttu-id="15a0c-176">Isso assegura que o nome da conta usado transmitirá a validação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15a0c-176">This ensures that the account name used will pass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validation.</span></span>  
  
 <span data-ttu-id="15a0c-177">Quando *IsWindowsUser* é definido como `false` , o script gerado concede a função **RSExec** no banco de dados do servidor de relatório, no banco de dados temporário do servidor de relatório e no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="15a0c-177">When *IsWindowsUser* is set to `false`, the generated script grants the **RSExec** role on the report server database, the report server temporary database, and the MSDB database.</span></span>  
  
 <span data-ttu-id="15a0c-178">Quando *IsWindowsUser* é definido como `false` , o usuário de SQL Server já deve existir no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que o script seja executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="15a0c-178">When *IsWindowsUser* is set to `false`, the SQL Server user must already exist on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the script to run successfully.</span></span>  
  
 <span data-ttu-id="15a0c-179">Se o servidor de relatório não tiver um banco de dados do servidor de relatório especificado, a ação de chamar GrantRightsToDatabaseUser retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="15a0c-179">If the report server does not have a report server database specified, calling GrantRightsToDatabaseUser returns an error.</span></span>  
  
 <span data-ttu-id="15a0c-180">O script gerado dá suporte ao [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 e ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15a0c-180">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a0c-181">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15a0c-181">Requirements</span></span>  
 <span data-ttu-id="15a0c-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a0c-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a0c-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15a0c-183">See Also</span></span>  
 [<span data-ttu-id="15a0c-184">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="15a0c-184">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
