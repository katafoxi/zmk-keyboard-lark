# ZMK Module Template

This repository contains a template for a ZMK module, as it would most frequently be used. 

## Usage

Read through the [ZMK Module Creation](https://zmk.dev/docs/development/module-creation) page for details on how to configure this template.

## More Info

For more info on modules, you can read through  through the [Zephyr modules page](https://docs.zephyrproject.org/3.5.0/develop/modules.html) and [ZMK's page on using modules](https://zmk.dev/docs/features/modules). [Zephyr's west manifest page](https://docs.zephyrproject.org/3.5.0/develop/west/manifest.html#west-manifests) may also be of use.

## WINDOWS. Для установки расширенной хост-раскладки 
[Расширенная раскладка](https://docs.google.com/spreadsheets/d/1xXg7V_umpOhjsuPLZJ3ickMg2kA1LSvM3Gqmz-Sg8EQ/edit?gid=335215024#gid=335215024)
- Распаковать "host_keymap/lark_win_hostkeymap_01.7z"
- Установить "setup.exe"
- В ОС переключиться на новоустановленный язык ввода (будет что-то вроде "Английский (Австралия) Русский - Custom)
- Основной режим "Английский (Австралия)", при включении режима CAPS lock раскладка выдает русские символы.
- Внести изменения в раскладку можно через программу [MSKLC](https://www.microsoft.com/en-us/download/details.aspx?id=102134) загрузив и отредактировав [исходник](/host_keymap/LARK_WIN_hostkeymap_01.klc).
- После валидации и сборки раскладки в MSKLC, старую Английский (Австралия) раскладку удалить, новую установить.

## LINUX. Для установки расширенной хост-раскладки.
Идем по адресу "/usr/share/X11/xkb/symbols"
Будем редактировать файлики AU и RU

Для  английского  выбираем английский (австралийский) "/usr/share/X11/xkb/symbols/AU" , как легкого к поиску и добавлению.
Заменяем стандартное содержимое на 

```txt
//
// Default Australian is the same as American
//
default  partial alphanumeric_keys
xkb_symbols "basic" 
{
    include "us(basic)"

    name[Group1]= "English (Australian)";


    // ┌──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┐
    // │ `~   │ !?1` │ "'2² │ #№3³ │ []4« │ ()5» │ ^$6  │ &@7  │ *%8  │ {}9  │ <>0° │ -_±  │ _=≠  │
    // │ TLDE │      │      │      │      │      │      │      │      │      │      │      │      │ 
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    // │      │ qQøØ │ wW&ς │ eE&ε │ rR ρ │ tTΔτ │ yY υ │ uUΘθ │ iI ι │ oOΩ  │ pPπ  │ ([{« │ )]}» │
    // │      │      │      │      │      │      │      │      │      │      │      │      │      │  
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    // │      │ aA@α │ sS$σ │ dD%δ │ fF^φ │ gGΣγ │ hH η │ jJ ξ │ kK   │ lL λ │ ;:   │ '"   │ \|   │
    // │      │      │      │      │      │      │      │      │      │      │      │      │ BKSL │ 
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    // │      │ zZ°ζ │ xX×χ │ cCΨψ │ vV ω │ bB β │ nN ν │ mM μ │ ,;   │ .:   │ /|\  │
    // │      │      │      │      │      │      │      │      │      │      │      │ 
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    // 
    // First row
    key <TLDE> {[ grave,            asciitilde,     NoSymbol,             NoSymbol              ]}; // ` ~
    key <AE01> {[ exclam,           question,       1,                    grave                 ]}; // ! ? 1 `
    key <AE02> {[ quotedbl,         apostrophe,     2,                    twosuperior           ]}; // " ' 2 ²
    key <AE03> {[ numbersign,       numerosign,     3,                    threesuperior         ]}; // # № 3 ³ 
    key <AE04> {[ bracketleft,      bracketright,   4,                    guillemotleft         ]}; // [ ] 4 «
    key <AE05> {[ parenleft,        parenright,     5,                    guillemotright        ]}; // ( ) 5 »
    key <AE06> {[ asciicircum,      dollar,         6,                    NoSymbol              ]}; // ^ $ 6
    key <AE07> {[ ampersand,        at,             7,                    NoSymbol              ]}; // & @ 7 
    key <AE08> {[ asterisk,         percent,        8,                    NoSymbol              ]}; // * % 8
    key <AE09> {[ braceleft,        braceright,     9,                    NoSymbol              ]}; // { } 9
    key <AE10> {[ less,             greater,        0,                    degree                ]}; // < > 0 °
    key <AE11> {[ minus,            underscore,     plusminus,            NoSymbol              ]}; // - _ ±
    key <AE12> {[ underscore,       equal,          notequal,             NoSymbol              ]}; // _ = ≠

    // Second row                   
    key <AD01> {[ q,                Q,              oslash,               Ooblique              ]}; // q Q ø Ø
    key <AD02> {[ w,                W,              ampersand,            Greek_finalsmallsigma ]}; // w W & ς
    key <AD03> {[ e,                E,              ampersand,            Greek_epsilon         ]}; // e E & ε
    key <AD04> {[ r,                R,              NoSymbol,             Greek_rho             ]}; // r R   ρ
    key <AD05> {[ t,                T,              Greek_DELTA,          Greek_tau             ]}; // t T Δ τ
    key <AD06> {[ y,                Y,              NoSymbol,             Greek_upsilon         ]}; // y Y   υ
    key <AD07> {[ u,                U,              Greek_THETA,          Greek_theta           ]}; // u U Θ θ
    key <AD08> {[ i,                I,              NoSymbol,             Greek_iota            ]}; // i I   ι
    key <AD09> {[ o,                O,              Greek_OMEGA,          NoSymbol              ]}; // o O Ω
    key <AD10> {[ p,                P,              NoSymbol,             Greek_pi              ]}; // p P   π
    key <AD11> {[ parenleft,        bracketleft,    braceleft,            guillemotleft         ]}; // ( [ { «
    key <AD12> {[ parenright,       bracketright,   braceright,           guillemotright        ]}; // ) ] } »
  
    // Third row
    key <AC01> {[ a,                A,              at,                   Greek_alpha           ]}; // a A @ α
    key <AC02> {[ s,                S,              dollar,               Greek_sigma           ]}; // s S $ σ
    key <AC03> {[ d,                D,              percent,              Greek_delta           ]}; // d D % δ
    key <AC04> {[ f,                F,              asciicircum,          Greek_phi             ]}; // f F ^ φ
    key <AC05> {[ g,                G,              Greek_SIGMA,          Greek_gamma           ]}; // g G Σ γ
    key <AC06> {[ h,                H,              NoSymbol,             Greek_eta             ]}; // h H   η
    key <AC07> {[ j,                J,              NoSymbol,             Greek_xi              ]}; // j J   ξ
    key <AC08> {[ k,                K,              NoSymbol,             NoSymbol              ]}; // k K
    key <AC09> {[ l,                L,              NoSymbol,             Greek_lambda          ]}; // l L   λ
    key <AC10> {[ semicolon,        colon,          NoSymbol,             NoSymbol              ]}; // ; :
    key <AC11> {[ apostrophe,       quotedbl,       NoSymbol,             NoSymbol              ]}; // ' "

    // Fourth row
    // key <LSGT> {[ less,          greater,        lessthanequal,        greaterthanequal      ]}; // < > ≤ ≥
    key <AB01> {[ z,                Z,              degree,               Greek_zeta            ]}; // z Z ° ζ
    key <AB02> {[ x,                X,              multiply,             Greek_chi             ]}; // x X × χ
    key <AB03> {[ c,                C,              Greek_PSI,            Greek_psi             ]}; // c C Ψ ψ
    key <AB04> {[ v,                V,              NoSymbol,             Greek_omega           ]}; // v V   ω
    key <AB05> {[ b,                B,              NoSymbol,             Greek_beta            ]}; // b B   β
    key <AB06> {[ n,                N,              NoSymbol,             Greek_nu              ]}; // n N   ν a
    key <AB07> {[ m,                M,              NoSymbol,             Greek_mu              ]}; // m M   μ
    key <AB08> {[ comma,            semicolon,      NoSymbol,             NoSymbol              ]}; // , ;
    key <AB09> {[ period,           colon,          NoSymbol,             NoSymbol              ]}; // . :
    key <AB10> {[ slash,            question,       backslash,            NoSymbol              ]}; // / | \
    key <BKSL> {[ backslash,        bar,            backslash,	          NoSymbol              ]}; // \ |
    
    // Rebind right Super (windows key) into a Compose key
    key <RWIN> {[ Multi_key ]};
    
    // Implement AltGr and AltGr+Shift
    // For some reason, include "level3(ralt_switch)" doesn't do the trick.
    
    key <RALT> {
        type[Group1]="TWO_LEVEL",
        [ ISO_Level3_Shift, Multi_key ]
    };
    modifier_map Mod5 { <RALT> };

};

```
Для расширения руской раскладки редактируем файл "/usr/share/X11/xkb/symbols/RU".
Открываем файл, ищем секцию "legacy" и заменяем её содержимое на следующее:

```txt
partial alphanumeric_keys
xkb_symbols "legacy" {

    include "ru(common)"
    name[Group1]= "Russian (legacy)";
    //
    // ┌──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┐
    // │ `~   │ !?1` │ "'2² │ #№3³ │ []4« │ ()5» │ ^$6  │ &@7  │ *%8  │ {}9  │ <>0° │ хХ±  │ _=≠  │
    // │ TLDE │      │      │      │      │      │      │      │      │      │      │      │      │ 
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    // │      │ йЙøØ │ цЦ&ς │ уУ&ε │ кК ρ │ еЕёЁ │ нН υ │ гГΘθ │ шШ ι │ щЩΩ  │ зЗπ  │ бБ{« │ юЮ}» │
    // │      │      │      │      │      │      │      │      │      │      │      │      │      │  
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    // │      │ фФ@α │ ыЫ$σ │ вВ%δ │ аА^φ │ пПΣγ │ рР η │ оО ξ │ лЛ   │ дД λ │ жЖ   │ эЭ   │ \|   │
    // │      │      │      │      │      │      │      │      │      │      │      │      │ BKSL │ 
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    // │      │ яЯ°ζ │ чЧ×χ │ сСΨψ │ мМ ω │ иИ β │ тТ ν │ ьЬъЪ │ ,;   │ .:   │ /|\  │
    // │      │      │      │      │      │      │      │      │      │      │      │ 
    // ├──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼
    //

    // First row
    key <TLDE> {[ grave,            asciitilde,     NoSymbol,             NoSymbol              ]}; // ` ~
    key <AE01> {[ exclam,           question,       1,                    grave                 ]}; // ! ? 1 `
    key <AE02> {[ quotedbl,         apostrophe,     2,                    twosuperior           ]}; // " ' 2 ²
    key <AE03> {[ numbersign,       numerosign,     3,                    threesuperior         ]}; // # № 3 ³ 
    key <AE04> {[ bracketleft,      bracketright,   4,                    guillemotleft         ]}; // [ ] 4 «
    key <AE05> {[ parenleft,        parenright,     5,                    guillemotright        ]}; // ( ) 5 »
    key <AE06> {[ asciicircum,      dollar,         6,                    NoSymbol              ]}; // ^ $ 6
    key <AE07> {[ ampersand,        at,             7,                    NoSymbol              ]}; // & @ 7 
    key <AE08> {[ asterisk,         percent,        8,                    NoSymbol              ]}; // * % 8
    key <AE09> {[ braceleft,        braceright,     9,                    NoSymbol              ]}; // { } 9
    key <AE10> {[ less,             greater,        0,                    degree                ]}; // < > 0 °
    key <AE11> {[ Cyrillic_ha,      Cyrillic_HA,    plusminus,            NoSymbol              ]}; // - _ ±
    key <AE12> {[ underscore,       equal,          notequal,             NoSymbol              ]}; // _ = ≠

    // Second row                   
    key <AD01> {[ Cyrillic_shorti, Cyrillic_SHORTI, oslash,               Ooblique              ]}; // q Q ø Ø
    key <AD02> {[ Cyrillic_tse,    Cyrillic_TSE,    ampersand,            Greek_finalsmallsigma ]}; // w W & ς
    key <AD03> {[ Cyrillic_u,      Cyrillic_U,      ampersand,            Greek_epsilon         ]}; // e E & ε
    key <AD04> {[ Cyrillic_ka,     Cyrillic_KA,     NoSymbol,             Greek_rho             ]}; // r R   ρ
    key <AD05> {[ Cyrillic_ie,     Cyrillic_IE,     Cyrillic_io,          Cyrillic_IO           ]}; // t T ё Ё
    key <AD06> {[ Cyrillic_en,     Cyrillic_EN,     NoSymbol,             Greek_upsilon         ]}; // y Y   υ
    key <AD07> {[ Cyrillic_ghe,    Cyrillic_GHE,    Greek_THETA,          Greek_theta           ]}; // u U Θ θ
    key <AD08> {[ Cyrillic_sha,    Cyrillic_SHA,    NoSymbol,             Greek_iota            ]}; // i I   ι
    key <AD09> {[ Cyrillic_shcha,  Cyrillic_SHCH,   Greek_OMEGA,          NoSymbol              ]}; // o O Ω
    key <AD10> {[ Cyrillic_ze,     Cyrillic_ZE,     NoSymbol,             Greek_pi              ]}; // p P   π
    key <AD11> {[ Cyrillic_be,     Cyrillic_BE,     braceleft,            guillemotleft         ]}; // ( [ { «
    key <AD12> {[ Cyrillic_yu,     Cyrillic_YU,     braceright,           guillemotright        ]}; // ) ] } »
  
    // Third row
    key <AC01> {[ Cyrillic_ef,     Cyrillic_EF,     at,                   Greek_alpha           ]}; // a A @ α
    key <AC02> {[ Cyrillic_yeru,   Cyrillic_YERU,   dollar,               Greek_sigma           ]}; // s S $ σ
    key <AC03> {[ Cyrillic_ve,     Cyrillic_VE,     percent,              Greek_delta           ]}; // d D % δ
    key <AC04> {[ Cyrillic_a,      Cyrillic_A,      asciicircum,          Greek_phi             ]}; // f F ^ φ
    key <AC05> {[ Cyrillic_pe,     Cyrillic_PE,     Greek_SIGMA,          Greek_gamma           ]}; // g G Σ γ
    key <AC06> {[ Cyrillic_er,     Cyrillic_ER,     NoSymbol,             Greek_eta             ]}; // h H   η
    key <AC07> {[ Cyrillic_o,      Cyrillic_O,      NoSymbol,             Greek_xi              ]}; // j J   ξ
    key <AC08> {[ Cyrillic_el,     Cyrillic_EL,     NoSymbol,             NoSymbol              ]}; // k K
    key <AC09> {[ Cyrillic_de,     Cyrillic_DE,     NoSymbol,             Greek_lambda          ]}; // l L   λ
    key <AC10> {[ Cyrillic_zhe,    Cyrillic_ZHE,    NoSymbol,             NoSymbol              ]}; // ; :
    key <AC11> {[ Cyrillic_e,      Cyrillic_E,      NoSymbol,             NoSymbol              ]}; // ' "

    // Fourth row
    // key <LSGT> {[ less,          greater,        lessthanequal,        greaterthanequal      ]}; // < > ≤ ≥
    key <AB01> {[ Cyrillic_ya,      Cyrillic_YA,    degree,               Greek_zeta            ]}; // z Z ° ζ
    key <AB02> {[ Cyrillic_che,     Cyrillic_CHE,   multiply,             Greek_chi             ]}; // x X × χ
    key <AB03> {[ Cyrillic_es,      Cyrillic_ES,    Greek_PSI,            Greek_psi             ]}; // c C Ψ ψ
    key <AB04> {[ Cyrillic_em,      Cyrillic_EM,    NoSymbol,             Greek_omega           ]}; // v V   ω
    key <AB05> {[ Cyrillic_i,       Cyrillic_I,     NoSymbol,             Greek_beta            ]}; // b B   β
    key <AB06> {[ Cyrillic_te,      Cyrillic_TE,    NoSymbol,             Greek_nu              ]}; // n N   ν a
    key <AB07> {[ Cyrillic_softsign, Cyrillic_SOFTSIGN, Cyrillic_hardsign, Cyrillic_HARDSIGN    ]}; // m M   μ
    key <AB08> {[ comma,            semicolon,      NoSymbol,             NoSymbol              ]}; // , ;
    key <AB09> {[ period,           colon,          NoSymbol,             NoSymbol              ]}; // . :
    key <AB10> {[ slash,            question,       backslash,            NoSymbol              ]}; // / | \
    key <BKSL> {[ backslash,        bar,            backslash,	          NoSymbol              ]}; // \ |
    
    // Rebind right Super (windows key) into a Compose key
    key <RWIN> {[ Multi_key ]};
    
    // Implement AltGr and AltGr+Shift
    // For some reason, include "level3(ralt_switch)" doesn't do the trick.
    
    key <RALT> {
        type[Group1]="TWO_LEVEL",
        [ ISO_Level3_Shift, Multi_key ]
    };
    modifier_map Mod5 { <RALT> };

};
```

Устанавливаем "английский (австралия)" и "русская (legasy)".

```bash
sudo apt-get install gnome-tweak-tool
gnome-tweaks
```




