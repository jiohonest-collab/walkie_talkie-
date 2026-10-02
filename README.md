<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Walkie Talkie - Blue Edition</title>
<!-- Brand Logo Favicon (Inline SVG Data URI) -->
<link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64'%3E%3Cdefs%3E%3ClinearGradient id='g' x1='0' y1='0' x2='64' y2='64' gradientUnits='userSpaceOnUse'%3E%3Cstop stop-color='%230084ff'/%3E%3Cstop offset='1' stop-color='%23005bb5'/%3E%3C/linearGradient%3E%3C/defs%3E%3Crect width='64' height='64' rx='16' fill='url(%23g)'/%3E%3Cpath d='M18 20C18 16.7 20.7 14 24 14H40C43.3 14 46 16.7 46 20V34C46 37.3 43.3 40 40 40H30L22 46V40H24C20.7 40 18 37.3 18 34V20Z' fill='white'/%3E%3Cpath d='M26 27C26 25 28 23 32 23C36 23 38 25 38 27' stroke='%230084ff' stroke-width='2.6' stroke-linecap='round' fill='none'/%3E%3Cpath d='M28.5 30.5C28.5 29.5 29.8 28.5 32 28.5C34.2 28.5 35.5 29.5 35.5 30.5' stroke='%230084ff' stroke-width='2.6' stroke-linecap='round' fill='none'/%3E%3Ccircle cx='32' cy='34' r='1.5' fill='%230084ff'/%3E%3C/svg%3E">

<style>
:root{
  --wa-teal:#0084ff;         /* WhatsApp / Messenger Royal Blue */
  --wa-teal-dark:#005bb5;    /* Deep Royal Blue */
  --wa-teal-light:#38bdf8;   /* Sky Blue */
  --wa-green:#0084ff;        /* Primary Blue */
  --wa-bg:#edf2f7;           /* Light soft background */
  --wa-panel:#ffffff;
  --wa-sidebar:#f8fafc;
  --wa-line:#e2e8f0;
  --wa-text:#0f172a;
  --wa-mute:#64748b;
  --wa-sub:#94a3b8;
  --wa-bubble-me:#dbeafe;    /* Light Royal Blue bubble */
  --wa-bubble-them:#ffffff;
  --wa-tick-blue:#0284c7;    /* Distinct vibrant Blue Double Tick */
  --wa-tick-grey:#94a3b8;
  --wa-amber:#f59e0b;
  --wa-red:#ef4444;
  --wa-biz-badge:#2563eb;
}
*{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%;font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;background:#e2e8f0;color:var(--wa-text);overflow:hidden}
button{font:inherit;color:inherit;cursor:pointer;border:0;background:none;outline:none}
button:disabled{cursor:not-allowed;opacity:.45}
input,select,textarea{font:inherit;color:inherit;outline:none}
[hidden]{display:none!important}

/* Main app container */
#app{
  height:100%;
  display:grid;
  grid-template-columns:400px 1fr;
  max-width:1650px;
  margin:0 auto;
  background:var(--wa-panel);
  box-shadow:0 8px 24px rgba(15,23,42,.12);
  position:relative;
}

/* Sidebar */
#side{
  display:flex;
  flex-direction:column;
  border-right:1px solid var(--wa-line);
  background:var(--wa-sidebar);
  height:100%;
  min-height:0;
  z-index:2;
}

/* Brand header */
.side-header{
  height:62px;
  background:var(--wa-sidebar);
  display:flex;
  align-items:center;
  padding:10px 16px;
  gap:10px;
  border-bottom:1px solid var(--wa-line);
  flex:none;
}
.brand-box{
  display:flex;
  align-items:center;
  gap:8px;
  margin-right:auto;
  cursor:pointer;
}
.app-logo-svg{
  width:32px;
  height:32px;
  flex:none;
  filter:drop-shadow(0 2px 4px rgba(0,132,255,.3));
}
.brand-title{
  font-weight:700;
  font-size:1.05rem;
  background:linear-gradient(135deg, #0084ff 0%, #005bb5 100%);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
  letter-spacing:-.3px;
}
.my-av-box{position:relative;cursor:pointer;flex:none}
.my-av-box:hover::after{
  content:'📷';position:absolute;inset:0;background:rgba(0,0,0,.45);border-radius:50%;display:grid;place-items:center;font-size:.9rem;color:#fff;
}
.av{
  width:40px;height:40px;border-radius:50%;background:#e2e8f0;color:#475569;display:grid;place-items:center;font-weight:700;font-size:.95rem;position:relative;flex:none;
}
.av img{position:absolute;inset:0;width:100%;height:100%;border-radius:50%;object-fit:cover;z-index:1}
.av span{z-index:1}
.av .dot{
  position:absolute;right:0;bottom:0;width:11px;height:11px;border-radius:50%;background:#aaa;border:2px solid #fff;z-index:2;
}
.av .dot.on{background:var(--wa-teal)}
.av.lg{width:76px;height:76px;font-size:2rem}
.av.lg .dot{width:16px;height:16px;right:2px;bottom:2px}
.av.group-av{background:linear-gradient(135deg, #0084ff, #005bb5);color:#fff}

.icon-btn{
  width:36px;height:36px;border-radius:50%;display:grid;place-items:center;color:#475569;transition:background .15s,color .15s;font-size:1.1rem;
}
.icon-btn:hover{background:rgba(0,132,255,.1);color:var(--wa-teal)}

/* Top Sidebar Navigation Tabs (Chats, Status, Channels) */
.nav-tabs-bar{
  display:flex;
  background:#fff;
  border-bottom:1px solid var(--wa-line);
  height:48px;
  flex:none;
}
.nav-tab{
  flex:1;
  display:flex;
  align-items:center;
  justify-content:center;
  gap:6px;
  font-size:.86rem;
  font-weight:600;
  color:var(--wa-mute);
  cursor:pointer;
  position:relative;
  border-bottom:2.5px solid transparent;
  transition:all .15s;
}
.nav-tab:hover{color:var(--wa-teal);background:rgba(0,132,255,.03)}
.nav-tab.active{color:var(--wa-teal);border-bottom-color:var(--wa-teal)}
.tab-badge-dot{
  width:7px;height:7px;border-radius:50%;background:var(--wa-teal);position:absolute;top:10px;right:18%;
}

/* User Badges */
.biz-badge{
  background:#eff6ff;color:#2563eb;border:1px solid #bfdbfe;font-size:.65rem;font-weight:700;padding:1px 6px;border-radius:4px;display:inline-flex;align-items:center;gap:3px;
}
#admin-badge{
  background:#0f172a;color:#fff;font-size:.65rem;font-weight:800;padding:1px 6px;border-radius:4px;cursor:pointer;
}

/* Search & filter row */
.search-row{
  padding:8px 12px;
  background:#fff;
  border-bottom:1px solid var(--wa-line);
  display:flex;
  gap:8px;
  align-items:center;
}
.search-box{
  flex:1;background:var(--wa-sidebar);border-radius:10px;display:flex;align-items:center;padding:0 12px;height:38px;gap:8px;border:1px solid transparent;transition:border-color .15s;
}
.search-box:focus-within{border-color:var(--wa-teal);background:#fff}
.search-box input{flex:1;border:0;background:none;font-size:.88rem;color:var(--wa-text)}
.filter-tabs{
  display:flex;gap:6px;padding:6px 12px;background:#fff;border-bottom:1px solid var(--wa-line);overflow-x:auto;
}
.ftab{
  padding:4px 12px;border-radius:16px;font-size:.78rem;font-weight:600;color:var(--wa-mute);background:var(--wa-sidebar);transition:all .15s;white-space:nowrap;
}
.ftab.on{background:#dbeafe;color:var(--wa-teal)}

/* Sidebar Panes */
.side-pane{flex:1;overflow-y:auto;display:flex;flex-direction:column;min-height:0;background:#fff}

/* Chats list */
#chats-list{list-style:none}
#chats-list li{
  display:flex;align-items:center;gap:12px;padding:11px 16px;cursor:pointer;border-bottom:1px solid #f8fafc;transition:background .12s;position:relative;
}
#chats-list li:hover{background:#f1f5f9}
#chats-list li.active{background:#e0f2fe}
.chat-info{flex:1;min-width:0;display:flex;flex-direction:column;gap:3px}
.chat-top-row{display:flex;justify-content:space-between;align-items:baseline}
.chat-name{font-weight:600;font-size:.92rem;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;color:var(--wa-text);display:flex;align-items:center;gap:4px}
.chat-time{font-size:.72rem;color:var(--wa-mute);flex:none;margin-left:6px}
.chat-bottom-row{display:flex;justify-content:space-between;align-items:center}
.chat-snippet{font-size:.82rem;color:var(--wa-mute);overflow:hidden;text-overflow:ellipsis;white-space:nowrap;flex:1}
.chat-badge{
  background:var(--wa-teal);color:#fff;font-size:.7rem;font-weight:700;min-width:19px;height:19px;border-radius:10px;padding:0 5px;display:inline-grid;place-items:center;margin-left:6px;flex:none;
}

/* ========================================================
   STATUS TAB STYLES
   ======================================================== */
.status-section{padding:14px 16px;border-bottom:1px solid var(--wa-line)}
.status-header{font-size:.78rem;font-weight:700;color:var(--wa-mute);text-transform:uppercase;letter-spacing:.5px;margin-bottom:10px}
.my-status-card{
  display:flex;align-items:center;gap:12px;padding:8px;border-radius:12px;cursor:pointer;transition:background .12s;
}
.my-status-card:hover{background:#f8fafc}
.status-ring{
  width:46px;height:46px;border-radius:50%;padding:2px;display:grid;place-items:center;position:relative;flex:none;
  border:2.5px solid var(--wa-teal);
}
.status-ring.viewed{border-color:var(--wa-sub)}
.status-ring.add-btn::after{
  content:'+';position:absolute;bottom:0;right:0;width:17px;height:17px;border-radius:50%;background:var(--wa-teal);color:#fff;font-size:1.1rem;display:grid;place-items:center;border:2px solid #fff;line-height:1;font-weight:700;
}
.status-actions-bar{display:flex;gap:8px;margin-top:10px}
.btn-status-act{
  flex:1;padding:8px 12px;border-radius:20px;font-size:.8rem;font-weight:600;display:flex;align-items:center;justify-content:center;gap:6px;background:var(--wa-sidebar);border:1px solid var(--wa-line);transition:background .15s;
}
.btn-status-act:hover{background:#e2e8f0;color:var(--wa-teal)}
.status-list{list-style:none}
.status-list li{
  display:flex;align-items:center;gap:12px;padding:10px 16px;cursor:pointer;border-bottom:1px solid #f8fafc;transition:background .12s;
}
.status-list li:hover{background:#f1f5f9}

/* ========================================================
   CHANNELS TAB STYLES
   ======================================================== */
.channel-banner{
  padding:14px 16px;background:linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);border-bottom:1px solid #bfdbfe;display:flex;flex-direction:column;gap:6px;
}
.channel-create-btn{
  background:var(--wa-teal);color:#fff;padding:8px 16px;border-radius:20px;font-weight:600;font-size:.85rem;display:inline-flex;align-items:center;gap:6px;align-self:flex-start;box-shadow:0 2px 6px rgba(0,132,255,.25);
}
.channel-list{list-style:none}
.channel-list li{
  display:flex;align-items:center;gap:12px;padding:12px 16px;cursor:pointer;border-bottom:1px solid #f1f5f9;transition:background .12s;
}
.channel-list li:hover{background:#f8fafc}
.channel-btn-follow{
  padding:5px 14px;border-radius:16px;font-size:.78rem;font-weight:700;border:1px solid var(--wa-teal);color:var(--wa-teal);background:#fff;transition:all .15s;flex:none;
}
.channel-btn-follow.following{background:var(--wa-sidebar);border-color:var(--wa-line);color:var(--wa-mute)}

/* Main chat section */
#main-chat{
  display:flex;
  flex-direction:column;
  height:100%;
  min-height:0;
  position:relative;
  background:#edf2f7;
  background-image:
    radial-gradient(circle at 10% 20%, rgba(0,132,255,.03) 0%, transparent 20%),
    radial-gradient(circle at 90% 80%, rgba(0,91,181,.03) 0%, transparent 25%);
}

/* Empty state */
#no-chat{
  flex:1;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  text-align:center;
  padding:32px;
  gap:16px;
  color:var(--wa-mute);
}
#no-chat h2{color:var(--wa-text);font-weight:600;font-size:1.75rem;margin-top:4px}
#no-chat p{font-size:.92rem;line-height:1.55;max-width:480px}
.no-chat-logo{width:88px;height:88px;filter:drop-shadow(0 8px 20px rgba(0,132,255,.25))}

/* Chat header */
#chat-header{
  height:62px;
  background:var(--wa-sidebar);
  border-bottom:1px solid var(--wa-line);
  display:flex;
  align-items:center;
  padding:8px 16px;
  gap:10px;
  z-index:2;
  flex:none;
}
.back-btn{display:none;font-size:1.5rem;color:var(--wa-text);padding:0 6px 0 0}
.chat-header-center{flex:1;min-width:0;cursor:pointer}
.chat-header-name{font-weight:600;font-size:1rem;color:var(--wa-text);overflow:hidden;text-overflow:ellipsis;white-space:nowrap;display:flex;align-items:center;gap:6px}
.chat-header-status{font-size:.76rem;color:var(--wa-mute);overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.chat-header-acts{display:flex;align-items:center;gap:4px}
.wt-toggle-btn{
  background:#eff6ff;color:var(--wa-teal);font-weight:600;font-size:.82rem;padding:6px 12px;border-radius:18px;display:flex;align-items:center;gap:5px;border:1px solid #bfdbfe;
}
.wt-toggle-btn:hover{background:#dbeafe}
.wt-toggle-btn.live{background:var(--wa-red);color:#fff;border-color:var(--wa-red);animation:ring 1s infinite}

/* Live audio reception banner */
#audio-banner{
  display:none;
  align-items:center;
  gap:10px;
  background:var(--wa-teal-dark);
  color:#fff;
  padding:8px 16px;
  z-index:3;
  box-shadow:0 2px 6px rgba(0,0,0,.15);
}
#audio-banner.on{display:flex}
.eq-bars{display:flex;gap:3px;align-items:center;height:18px}
.eq-bars i{width:3px;height:100%;background:#38bdf8;border-radius:2px;animation:eq .6s infinite ease-in-out alternate}
.eq-bars i:nth-child(2){animation-delay:.15s}.eq-bars i:nth-child(3){animation-delay:.3s}.eq-bars i:nth-child(4){animation-delay:.45s}
@keyframes eq{from{transform:scaleY(.2)}to{transform:scaleY(1)}}

/* Chat messages feed */
#messages-container{
  flex:1;
  overflow-y:auto;
  padding:16px 20px;
  display:flex;
  flex-direction:column;
  gap:6px;
  min-height:0;
}
.msg-date-badge{
  align-self:center;background:#ffffff;box-shadow:0 1px 2px rgba(15,23,42,.08);border-radius:8px;padding:5px 12px;font-size:.74rem;font-weight:600;color:#64748b;margin:8px 0;
}
.msg-row{
  display:flex;gap:8px;max-width:75%;position:relative;animation:fadeIn .15s ease-out;
}
@keyframes fadeIn{from{opacity:0;transform:translateY(4px)}to{opacity:1;transform:translateY(0)}}
.msg-row.me{align-self:flex-end;flex-direction:row-reverse}
.msg-row.them{align-self:flex-start}
.msg-bubble{
  padding:6px 10px 5px 11px;
  border-radius:10px;
  font-size:.9rem;
  line-height:1.42;
  word-break:break-word;
  position:relative;
  box-shadow:0 1px 1px rgba(15,23,42,.08);
  min-width:80px;
}
.msg-row.me .msg-bubble{background:var(--wa-bubble-me);border-top-right-radius:0}
.msg-row.them .msg-bubble{background:var(--wa-bubble-them);border-top-left-radius:0}
.msg-sender{
  font-size:.76rem;font-weight:700;color:#e542a3;margin-bottom:2px;display:flex;align-items:center;gap:4px;
}
.msg-sender.c1{color:#1f7aec}.msg-sender.c2{color:#07bc0c}.msg-sender.c3{color:#ff8b00}.msg-sender.c4{color:#b339ff}
.msg-content{color:var(--wa-text)}
.msg-foot{
  display:flex;align-items:center;justify-content:flex-end;gap:3px;font-size:.68rem;color:var(--wa-mute);margin-top:2px;float:right;margin-left:10px;
}
.tick{font-size:.78rem;font-weight:700;letter-spacing:-1px}
.tick.sent{color:var(--wa-tick-grey)}
.tick.delivered{color:var(--wa-tick-grey)}
.tick.read{color:var(--wa-tick-blue)}
.tick.pending{color:var(--wa-tick-grey);font-size:.7rem}

/* Image & document previews */
.chat-img-preview{
  max-width:100%;max-height:300px;border-radius:8px;object-fit:cover;cursor:pointer;display:block;margin-bottom:4px;transition:opacity .15s;
}
.chat-img-preview:hover{opacity:.92}
.chat-doc-card{
  display:flex;align-items:center;gap:10px;padding:8px 10px;background:rgba(0,0,0,.04);border-radius:8px;margin-bottom:4px;min-width:180px;
}
.chat-doc-icon{font-size:1.8rem;line-height:1}
.chat-doc-info{flex:1;min-width:0;display:flex;flex-direction:column}
.chat-doc-name{font-weight:600;font-size:.84rem;color:var(--wa-text);overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.chat-doc-size{font-size:.72rem;color:var(--wa-mute)}
.chat-doc-dl{
  color:var(--wa-teal);font-size:1.15rem;padding:4px;border-radius:50%;transition:background .15s;
}
.chat-doc-dl:hover{background:rgba(0,132,255,.1)}

/* Voice note player */
.vn-player{display:flex;align-items:center;gap:8px;padding:2px 0}
.vn-btn{
  width:32px;height:32px;border-radius:50%;background:var(--wa-teal);color:#fff;display:grid;place-items:center;font-size:.88rem;flex:none;
}
.vn-wave{display:flex;align-items:center;gap:2px;flex:1;height:24px}
.vn-bar{width:3px;background:var(--wa-teal);border-radius:2px}
.vn-dur{font-size:.7rem;color:var(--wa-mute);flex:none}

/* Attach menu */
.attach-menu{
  position:absolute;left:20px;bottom:70px;background:#fff;border-radius:16px;box-shadow:0 12px 32px rgba(15,23,42,.18);border:1px solid var(--wa-line);padding:10px;display:none;flex-direction:column;gap:4px;z-index:20;animation:popIn .15s ease-out;
}
.attach-menu.show{display:flex}
@keyframes popIn{from{opacity:0;transform:scale(.9) translateY(10px)}to{opacity:1;transform:scale(1) translateY(0)}}
.attach-item{
  display:flex;align-items:center;gap:12px;padding:10px 16px;border-radius:10px;cursor:pointer;transition:background .12s;font-size:.88rem;font-weight:500;
}
.attach-item:hover{background:var(--wa-sidebar)}
.attach-icon{
  width:36px;height:36px;border-radius:50%;display:grid;place-items:center;font-size:1.15rem;color:#fff;
}
.attach-icon.img-bg{background:linear-gradient(135deg, #0084ff, #005bb5)}
.attach-icon.doc-bg{background:linear-gradient(135deg, #6366f1, #4338ca)}
.attach-icon.cam-bg{background:linear-gradient(135deg, #ec4899, #be185d)}

/* Chat input bar */
#chat-input-bar{
  background:var(--wa-sidebar);
  border-top:1px solid var(--wa-line);
  padding:10px 16px;
  display:flex;
  align-items:center;
  gap:10px;
  position:relative;
  z-index:3;
  flex:none;
}
.input-bubble{
  flex:1;background:#fff;border-radius:24px;display:flex;align-items:center;padding:0 12px;height:44px;gap:8px;box-shadow:0 1px 2px rgba(15,23,42,.06);border:1px solid var(--wa-line);
}
.input-bubble input{flex:1;border:0;background:none;font-size:.92rem;color:var(--wa-text)}
.btn-round{
  width:44px;height:44px;border-radius:50%;background:var(--wa-teal);color:#fff;display:grid;place-items:center;font-size:1.25rem;box-shadow:0 2px 8px rgba(0,132,255,.3);transition:transform .1s,background .15s;flex:none;
}
.btn-round:active{transform:scale(.94)}
.btn-round.mic-live{background:var(--wa-red);animation:pulse 1s infinite alternate}
@keyframes pulse{from{box-shadow:0 0 0 0 rgba(239,68,68,.7)}to{box-shadow:0 0 0 14px rgba(239,68,68,0)}}

/* Recording HUD */
#rec-hud{
  position:absolute;inset:0;background:var(--wa-sidebar);display:none;align-items:center;padding:0 20px;gap:12px;z-index:5;
}
#rec-hud.show{display:flex}
.rec-dot{width:12px;height:12px;border-radius:50%;background:var(--wa-red);animation:blink .8s infinite alternate}
@keyframes blink{from{opacity:1}to{opacity:.2}}
.rec-time{font-weight:700;font-size:1rem;color:var(--wa-red);min-width:45px}
.rec-slide{font-size:.85rem;color:var(--wa-mute);flex:1;text-align:center}

/* Floating PTT Walkie-Talkie Drawer */
#wt-drawer{
  position:absolute;bottom:75px;right:20px;width:280px;background:#fff;border-radius:20px;box-shadow:0 16px 40px rgba(15,23,42,.2);border:1px solid var(--wa-line);padding:20px;display:none;flex-direction:column;align-items:center;gap:12px;z-index:30;animation:popIn .2s ease-out;
}
#wt-drawer.show{display:flex}
.ptt-dial{
  width:110px;height:110px;border-radius:50%;background:linear-gradient(135deg, #0084ff 0%, #005bb5 100%);color:#fff;font-weight:800;font-size:1.2rem;letter-spacing:1px;box-shadow:0 8px 24px rgba(0,132,255,.4), inset 0 2px 4px rgba(255,255,255,.4);display:grid;place-items:center;user-select:none;transition:transform .1s,box-shadow .1s;
}
.ptt-dial:active,.ptt-dial.active{
  transform:scale(.92);background:var(--wa-red);box-shadow:0 4px 16px rgba(239,68,68,.5);
}
.drawer-close{position:absolute;top:10px;right:14px;color:var(--wa-mute);font-size:1.2rem}

/* ========================================================
   CALL OVERLAY & POPUP
   ======================================================== */
#call-overlay{
  position:fixed;inset:0;background:#0f172a;z-index:100;display:none;flex-direction:column;color:#fff;overflow:hidden;
}
#call-overlay.minimized{
  inset:auto 20px 80px auto;width:280px;height:380px;border-radius:16px;box-shadow:0 12px 32px rgba(0,0,0,.5);border:2px solid rgba(255,255,255,.2);
}
.call-top-bar{
  height:56px;display:flex;align-items:center;justify-content:space-between;padding:0 18px;z-index:10;background:linear-gradient(to bottom, rgba(0,0,0,.6), transparent);
}
.call-enc-badge{font-size:.76rem;color:#94a3b8;display:flex;align-items:center;gap:4px}
.call-timer{font-size:.9rem;font-weight:600;color:#fff}
.call-stage{
  flex:1;position:relative;display:flex;align-items:center;justify-content:center;overflow:hidden;
}
.remote-video{width:100%;height:100%;object-fit:cover;background:#000}
.call-audio-stage{display:flex;flex-direction:column;align-items:center;gap:12px;text-align:center;z-index:2}
.call-audio-stage .av{width:96px;height:96px;font-size:2.5rem}
.local-pip{
  position:absolute;top:16px;right:16px;width:110px;height:150px;border-radius:12px;overflow:hidden;box-shadow:0 6px 18px rgba(0,0,0,.4);border:2px solid rgba(255,255,255,.25);background:#000;z-index:5;
}
.local-pip video{width:100%;height:100%;object-fit:cover;transform:scaleX(-1)}
.call-controls{
  height:84px;background:linear-gradient(to top, rgba(0,0,0,.7), transparent);display:flex;align-items:center;justify-content:center;gap:20px;z-index:10;padding-bottom:env(safe-area-inset-bottom,0);
}
.call-btn{
  width:52px;height:52px;border-radius:50%;background:rgba(255,255,255,.2);color:#fff;display:grid;place-items:center;font-size:1.35rem;transition:background .15s,transform .1s;
}
.call-btn:active{transform:scale(.92)}
.call-btn.off{background:#fff;color:#0f172a}
.call-btn.end{background:var(--wa-red)}

/* Incoming call modal */
#inc-call-modal{
  position:fixed;inset:0;background:rgba(15,23,42,.85);display:none;place-items:center;z-index:120;padding:20px;
}
#inc-call-modal.show{display:grid}
.inc-card{
  background:#1e293b;color:#fff;border-radius:20px;padding:32px 24px;width:min(340px,100%);display:flex;flex-direction:column;align-items:center;gap:14px;text-align:center;box-shadow:0 24px 60px rgba(0,0,0,.6);border:1px solid rgba(255,255,255,.1);
}
.inc-card .av{width:88px;height:88px;font-size:2.4rem}
.inc-actions{display:flex;gap:40px;margin-top:16px}
.inc-act-btn{
  width:60px;height:60px;border-radius:50%;display:grid;place-items:center;font-size:1.6rem;color:#fff;box-shadow:0 4px 14px rgba(0,0,0,.4);
}
.inc-act-btn.accept{background:var(--wa-teal);animation:pulse 1s infinite alternate}
.inc-act-btn.decline{background:var(--wa-red)}

/* ========================================================
   STATUS STORY VIEWER MODAL
   ======================================================== */
#status-viewer{
  position:fixed;inset:0;background:#000;z-index:130;display:none;flex-direction:column;justify-content:space-between;
}
#status-viewer.show{display:flex}
.status-progress-bar-wrap{
  padding:12px 16px 0;display:flex;gap:4px;z-index:10;
}
.status-seg-track{flex:1;height:3px;background:rgba(255,255,255,.3);border-radius:2px;overflow:hidden}
.status-seg-fill{height:100%;background:#fff;width:0%;transition:width .1s linear}
.status-seg-fill.done{width:100%}
.status-top-user{
  display:flex;align-items:center;gap:10px;padding:12px 16px;color:#fff;z-index:10;
}
.status-viewer-content{
  flex:1;position:relative;display:flex;align-items:center;justify-content:center;padding:24px;color:#fff;text-align:center;
}
.status-text-slide{
  font-size:1.8rem;font-weight:700;line-height:1.4;max-width:560px;padding:30px;border-radius:20px;
}
.status-img-slide{
  max-width:100%;max-height:80vh;border-radius:12px;object-fit:contain;box-shadow:0 8px 30px rgba(0,0,0,.8);
}
.status-viewer-nav{
  position:absolute;inset:0;display:grid;grid-template-columns:1fr 1fr;z-index:5;
}
.status-nav-left,.status-nav-right{cursor:pointer}

/* Lightbox Modal */
#image-lightbox{
  position:fixed;inset:0;background:rgba(0,0,0,.92);display:none;place-items:center;z-index:110;padding:20px;
}
#image-lightbox.show{display:grid}
#lightbox-img{max-width:90vw;max-height:85vh;border-radius:8px;object-fit:contain}

/* Modals */
.modal-overlay{
  position:fixed;inset:0;background:rgba(15,23,42,.65);display:none;place-items:center;z-index:60;padding:16px;
}
.modal-overlay.show{display:grid}
.modal-card{
  background:#fff;border-radius:18px;width:min(440px,100%);max-height:90vh;display:flex;flex-direction:column;box-shadow:0 24px 48px rgba(15,23,42,.28);overflow:hidden;
}
.modal-head{
  height:58px;background:linear-gradient(135deg, #0084ff 0%, #005bb5 100%);color:#fff;display:flex;align-items:center;padding:0 18px;gap:12px;font-weight:600;font-size:1.05rem;flex:none;
}
.modal-body{
  padding:20px 22px;overflow-y:auto;display:flex;flex-direction:column;gap:14px;
}
.modal-foot{
  padding:14px 22px;background:#f8fafc;display:flex;justify-content:flex-end;gap:10px;border-top:1px solid var(--wa-line);
}
.input-field{
  width:100%;border:1px solid var(--wa-line);border-radius:10px;padding:11px 14px;font-size:.92rem;background:#fff;transition:border-color .15s;
}
.input-field:focus{border-color:var(--wa-teal)}
.btn-primary{
  background:var(--wa-teal);color:#fff;padding:10px 20px;border-radius:24px;font-weight:600;font-size:.9rem;box-shadow:0 2px 8px rgba(0,132,255,.3);transition:background .15s;
}
.btn-primary:hover{background:#0073e6}
.btn-secondary{
  background:#fff;color:var(--wa-text);border:1px solid var(--wa-line);padding:10px 18px;border-radius:24px;font-weight:600;font-size:.9rem;
}
.btn-danger{
  background:#fee2e2;color:var(--wa-red);border:1px solid #fecaca;padding:9px 16px;border-radius:20px;font-weight:600;font-size:.85rem;
}

/* Suggestion dropdown list */
.suggestions-box{
  border:1px solid var(--wa-line);border-radius:10px;background:#fff;max-height:160px;overflow-y:auto;list-style:none;box-shadow:0 4px 12px rgba(15,23,42,.08);margin-top:-6px;display:none;
}
.suggestions-box.show{display:block}
.suggestions-box li{
  display:flex;align-items:center;gap:10px;padding:8px 12px;border-bottom:1px solid #f1f5f9;cursor:pointer;transition:background .1s;
}
.suggestions-box li:hover{background:#f0f7ff}

/* Real-time simulated push banner */
#push-otp-banner{
  position:fixed;top:16px;left:50%;transform:translateX(-50%);background:#0f172a;color:#fff;border-radius:14px;padding:12px 18px;display:none;align-items:center;gap:12px;z-index:200;box-shadow:0 12px 32px rgba(0,0,0,.4);border:1px solid rgba(255,255,255,.15);animation:slideDown .25s ease-out;max-width:92%;
}
@keyframes slideDown{from{opacity:0;transform:translate(-50%,-20px)}to{opacity:1;transform:translate(-50%,0)}}
.otp-pill{
  background:#0284c7;color:#fff;font-weight:800;font-size:1.1rem;letter-spacing:2px;padding:3px 8px;border-radius:6px;
}

/* Toast */
#toast{
  position:fixed;left:50%;bottom:85px;transform:translateX(-50%);background:rgba(15,23,42,.92);color:#fff;padding:9px 18px;border-radius:20px;font-size:.88rem;display:none;max-width:90%;text-align:center;z-index:90;box-shadow:0 4px 12px rgba(0,0,0,.25);
}

/* Global Announcement Banner */
#admin-announcement-bar{
  display:none;background:#f59e0b;color:#000;padding:8px 16px;font-weight:700;font-size:.88rem;align-items:center;justify-content:space-between;z-index:9;box-shadow:0 2px 4px rgba(0,0,0,.15);
}

/* Responsive */
@media(max-width:768px){
  #app{grid-template-columns:1fr}
  #main-chat{display:none}
  #app.in-chat #side{display:none}
  #app.in-chat #main-chat{display:flex}
  .back-btn{display:block}
  #wt-drawer{bottom:80px;right:10px;left:10px;width:auto}
  #call-overlay.minimized{inset:auto 10px 70px auto;width:200px;height:260px}
  .attach-menu{left:12px;bottom:60px}
}
</style>
</head>
<body>

<div id="app">
 <!-- SIDEBAR -->
 <aside id="side">
  <div class="side-header">
   <!-- Website Logo & Title -->
   <div class="brand-box" id="btn-brand-home" title="Walkie Talkie Web - Home">
    <svg class="app-logo-svg" viewBox="0 0 64 64" fill="none">
     <defs>
      <linearGradient id="logoG" x1="0" y1="0" x2="64" y2="64" gradientUnits="userSpaceOnUse">
       <stop stop-color="#0084ff"/>
       <stop offset="1" stop-color="#005bb5"/>
      </linearGradient>
     </defs>
     <rect width="64" height="64" rx="16" fill="url(#logoG)"/>
     <path d="M18 20C18 16.7 20.7 14 24 14H40C43.3 14 46 16.7 46 20V34C46 37.3 43.3 40 40 40H30L22 46V40H24C20.7 40 18 37.3 18 34V20Z" fill="white"/>
     <path d="M26 27C26 25 28 23 32 23C36 23 38 25 38 27" stroke="#0084ff" stroke-width="2.6" stroke-linecap="round"/>
     <path d="M28.5 30.5C28.5 29.5 29.8 28.5 32 28.5C34.2 28.5 35.5 29.5 35.5 30.5" stroke="#0084ff" stroke-width="2.6" stroke-linecap="round"/>
     <circle cx="32" cy="34" r="1.5" fill="#0084ff"/>
    </svg>
    <span class="brand-title">WalkieTalkie</span>
   </div>

   <div class="my-av-box" id="my-av-btn" title="View & Edit Profile">
    <div class="av" id="my-av"><span id="my-av-letter">U</span></div>
   </div>

   <button class="icon-btn" id="btn-admin-panel" title="Admin Control" hidden>🛡️</button>
   <button class="icon-btn" id="btn-new-group" title="New Group">👥</button>
   <button class="icon-btn" id="btn-add-chat" title="Add Contact / Friend">➕</button>
   <button class="icon-btn" id="btn-my-settings" title="Profile & Settings">⚙️</button>
  </div>

  <!-- Top Navigation Switcher: Chats, Status, Channels -->
  <div class="nav-tabs-bar">
   <div class="nav-tab active" id="tab-btn-chats" data-tab="chats">
    <span>💬 Chats</span>
   </div>
   <div class="nav-tab" id="tab-btn-status" data-tab="status">
    <span>⭕ Status</span>
    <span class="tab-badge-dot" id="status-badge-dot" hidden></span>
   </div>
   <div class="nav-tab" id="tab-btn-channels" data-tab="channels">
    <span>📢 Channels</span>
   </div>
  </div>

  <!-- PANE 1: CHATS -->
  <div class="side-pane" id="pane-chats">
   <div class="search-row">
    <div class="search-box">
     <span style="color:var(--wa-mute)">🔍</span>
     <input id="search-input" placeholder="Search or start new chat">
    </div>
   </div>
   <div class="filter-tabs">
    <button class="ftab on" data-filter="all">All</button>
    <button class="ftab" data-filter="unread">Unread</button>
    <button class="ftab" data-filter="groups">Groups</button>
   </div>
   <ul id="chats-list"></ul>
  </div>

  <!-- PANE 2: STATUS / STORIES -->
  <div class="side-pane" id="pane-status" style="display:none">
   <div class="status-section">
    <div class="status-header">My Status</div>
    <div class="my-status-card" id="my-status-card">
     <div class="status-ring add-btn" id="my-status-ring">
      <div class="av" id="my-status-av"><span>U</span></div>
     </div>
     <div style="flex:1;min-width:0">
      <div style="font-weight:600;font-size:.92rem">My Status</div>
      <div style="font-size:.76rem;color:var(--wa-mute)" id="my-status-sub">Tap to add status update</div>
     </div>
    </div>
    <div class="status-actions-bar">
     <button class="btn-status-act" id="btn-post-text-status">
      <span>✏️</span> <span>Text Status</span>
     </button>
     <button class="btn-status-act" id="btn-post-photo-status">
      <span>📷</span> <span>Photo Status</span>
     </button>
    </div>
   </div>

   <div style="padding:14px 16px 6px">
    <div class="status-header">Recent Updates</div>
   </div>
   <ul class="status-list" id="status-feed-list"></ul>
  </div>

  <!-- PANE 3: CHANNELS -->
  <div class="side-pane" id="pane-channels" style="display:none">
   <div class="channel-banner">
    <div style="font-weight:700;font-size:.95rem;color:var(--wa-teal)">📢 WhatsApp Channels</div>
    <div style="font-size:.78rem;color:var(--wa-mute)">Stay updated on topics, announcements, and news.</div>
    <button class="channel-create-btn" id="btn-create-channel-open" style="margin-top:4px">
     <span>➕</span> <span>New Channel</span>
    </button>
   </div>
   <div style="padding:12px 16px 6px">
    <div class="status-header">Explore Channels</div>
   </div>
   <ul class="channel-list" id="channels-feed-list"></ul>
  </div>
 </aside>

 <!-- MAIN CHAT VIEW -->
 <main id="main-chat">
  <!-- Global Admin Broadcast Banner -->
  <div id="admin-announcement-bar">
   <div style="display:flex;align-items:center;gap:8px">
    <span>📢</span> <span id="admin-announcement-text">Announcement</span>
   </div>
   <button onclick="$('#admin-announcement-bar').style.display='none'" style="font-weight:700">✕</button>
  </div>

  <!-- No chat selected empty state -->
  <div id="no-chat">
   <svg class="no-chat-logo" viewBox="0 0 64 64" fill="none">
    <defs>
     <linearGradient id="logoLg" x1="0" y1="0" x2="64" y2="64" gradientUnits="userSpaceOnUse">
      <stop stop-color="#0084ff"/>
      <stop offset="1" stop-color="#005bb5"/>
     </linearGradient>
    </defs>
    <rect width="64" height="64" rx="16" fill="url(#logoLg)"/>
    <path d="M18 20C18 16.7 20.7 14 24 14H40C43.3 14 46 16.7 46 20V34C46 37.3 43.3 40 40 40H30L22 46V40H24C20.7 40 18 37.3 18 34V20Z" fill="white"/>
    <path d="M26 27C26 25 28 23 32 23C36 23 38 25 38 27" stroke="#0084ff" stroke-width="2.6" stroke-linecap="round"/>
    <path d="M28.5 30.5C28.5 29.5 29.8 28.5 32 28.5C34.2 28.5 35.5 29.5 35.5 30.5" stroke="#0084ff" stroke-width="2.6" stroke-linecap="round"/>
    <circle cx="32" cy="34" r="1.5" fill="#0084ff"/>
   </svg>
   <h2>WalkieTalkie Web</h2>
   <p>Send instant voice notes, text messages, photos, files, and make calls in high definition. Stay connected with friends, groups, and channels.</p>
   <button class="btn-primary" id="btn-start-chat" style="margin-top:10px">Start a New Chat</button>
  </div>

  <!-- Active conversation pane -->
  <div id="chat-pane" style="display:none;flex-direction:column;height:100%;min-height:0">
   <header id="chat-header">
    <button class="back-btn" id="btn-back" aria-label="Back">‹</button>
    <div class="av" id="header-av"><span>?</span></div>
    <div class="chat-header-center" id="header-info-click" title="Click to view contact/channel info">
     <div class="chat-header-name" id="chat-title">Friend</div>
     <div class="chat-header-status" id="chat-subtitle">offline</div>
    </div>
    <div class="chat-header-acts" id="chat-header-acts">
     <button class="icon-btn" id="btn-voice-call" title="Voice call">📞</button>
     <button class="icon-btn" id="btn-video-call" title="Video call">📹</button>
     <button class="wt-toggle-btn" id="btn-wt-toggle" title="Open Walkie Talkie dial">
      <span>📻</span> <span id="wt-btn-txt">Talk</span>
     </button>
     <button class="icon-btn" id="btn-chat-menu" title="Info">⋮</button>
    </div>
   </header>

   <!-- Live audio reception banner -->
   <div id="audio-banner">
    <div class="av" id="banner-av" style="width:32px;height:32px;font-size:.8rem"><span>?</span></div>
    <div style="flex:1;min-width:0">
     <div id="banner-name" style="font-weight:700;font-size:.88rem">Speaking...</div>
     <div style="font-size:.76rem;opacity:.9">Transmitting live audio</div>
    </div>
    <div class="eq-bars"><i></i><i></i><i></i><i></i></div>
   </div>

   <!-- Message bubbles feed -->
   <div id="messages-container"></div>

   <!-- Attachment Popup Menu -->
   <div id="attach-menu" class="attach-menu">
    <button type="button" class="attach-item" id="btn-attach-img" title="Photos & Videos">
     <span class="attach-icon img-bg">🖼️</span>
     <span>Photos</span>
    </button>
    <button type="button" class="attach-item" id="btn-attach-doc" title="Documents & Any Files">
     <span class="attach-icon doc-bg">📄</span>
     <span>Document</span>
    </button>
    <button type="button" class="attach-item" id="btn-attach-cam" title="Camera">
     <span class="attach-icon cam-bg">📷</span>
     <span>Camera</span>
    </button>
   </div>

   <!-- Chat input bar -->
   <div id="chat-input-bar">
    <div class="input-bubble">
     <button type="button" class="icon-btn" id="btn-emoji" title="Emoji" style="width:28px;height:28px;font-size:1.15rem">😊</button>
     <button type="button" class="icon-btn" id="btn-attach" title="Attach file or photo" style="width:28px;height:28px;font-size:1.15rem">📎</button>
     <input id="chat-input" placeholder="Type a message" autocomplete="off" maxlength="1000">
    </div>
    <button type="button" class="btn-round" id="btn-mic-send" title="Hold to record or tap to send">
     <span id="mic-send-icon">🎙️</span>
    </button>

    <!-- Recording HUD overlay -->
    <div id="rec-hud">
     <div class="rec-dot"></div>
     <div class="rec-time" id="rec-timer">0:00</div>
     <div class="rec-slide">‹ Slide left to cancel</div>
     <span style="font-size:.82rem;font-weight:600;color:var(--wa-red)">RELEASE TO SEND</span>
    </div>
   </div>

   <!-- Channel follower reaction bar (shown when viewing a channel you follow) -->
   <div id="channel-react-bar" style="display:none;background:var(--wa-sidebar);padding:10px 16px;border-top:1px solid var(--wa-line);align-items:center;justify-content:space-between">
    <div style="font-size:.84rem;color:var(--wa-mute);display:flex;align-items:center;gap:6px">
     <span>📢</span> <span>Broadcast channel (Read only)</span>
    </div>
    <div style="display:flex;gap:6px">
     <button class="icon-btn" onclick="reactChannel('❤️')" title="Love">❤️</button>
     <button class="icon-btn" onclick="reactChannel('👍')" title="Thumbs up">👍</button>
     <button class="icon-btn" onclick="reactChannel('🔥')" title="Fire">🔥</button>
     <button class="icon-btn" onclick="reactChannel('👏')" title="Clap">👏</button>
     <button class="icon-btn" onclick="reactChannel('🚀')" title="Rocket">🚀</button>
    </div>
   </div>

   <!-- Floating Walkie Talkie PTT Drawer -->
   <div id="wt-drawer">
    <button class="drawer-close" id="btn-close-wt">✕</button>
    <div style="font-weight:700;font-size:.92rem;color:var(--wa-teal)">Walkie Talkie Mode</div>
    <div style="font-size:.78rem;color:var(--wa-mute);text-align:center" id="wt-drawer-status">Hold button to speak live</div>
    <button class="ptt-dial" id="wt-ptt-btn">TALK</button>
    <div style="font-size:.72rem;color:var(--wa-mute)">Audio broadcasts instantly to this chat</div>
   </div>
  </div>
 </main>
</div>

<!-- ========================================================
     IMAGE LIGHTBOX
     ======================================================== -->
<div id="image-lightbox">
 <button class="icon-btn" id="btn-close-lightbox" style="position:absolute;top:16px;right:20px;color:#fff;font-size:1.6rem">✕</button>
 <a id="lightbox-dl-btn" href="#" download="photo.jpg" class="icon-btn" style="position:absolute;top:16px;right:68px;color:#fff;font-size:1.3rem;text-decoration:none" title="Download Image">⬇️</a>
 <img id="lightbox-img" src="" alt="Full view">
</div>

<!-- ========================================================
     WHATSAPP VOICE & VIDEO CALL OVERLAY
     ======================================================== -->
<div id="call-overlay">
 <div class="call-top-bar">
  <div class="call-enc-badge">🔒 End-to-end encrypted</div>
  <div class="call-timer" id="call-duration">00:00</div>
  <button class="icon-btn" id="btn-call-minimize" style="color:#fff;font-size:1rem" title="Minimize">🗗</button>
 </div>
 <div class="call-stage" id="call-stage">
  <video id="remote-video" class="remote-video" autoplay playsinline></video>
  <div class="call-audio-stage" id="call-audio-stage">
   <div class="av" id="call-stage-av"><span>?</span></div>
   <h2 id="call-stage-name" style="font-size:1.4rem">Friend</h2>
   <div id="call-status-label" style="font-size:.9rem;color:#94a3b8">Calling...</div>
  </div>
  <div class="local-pip" id="local-pip">
   <video id="local-video" autoplay playsinline muted></video>
  </div>
 </div>
 <div class="call-controls">
  <button class="call-btn" id="btn-toggle-cam" title="Camera on/off">📷</button>
  <button class="call-btn" id="btn-toggle-mic" title="Mute/unmute">🎤</button>
  <button class="call-btn end" id="btn-end-call" title="End call">📴</button>
 </div>
</div>

<!-- INCOMING CALL POPUP -->
<div id="inc-call-modal">
 <div class="inc-card">
  <div class="av" id="inc-av"><span>?</span></div>
  <h3 id="inc-caller-name" style="font-size:1.25rem">Friend</h3>
  <div id="inc-call-type-text" style="color:#94a3b8;font-size:.88rem">Incoming Call...</div>
  <div class="inc-actions">
   <button class="inc-act-btn decline" id="btn-inc-decline" title="Decline">📴</button>
   <button class="inc-act-btn accept" id="btn-inc-accept" title="Answer">📞</button>
  </div>
 </div>
</div>

<!-- ========================================================
     STATUS / STORY VIEWER
     ======================================================== -->
<div id="status-viewer">
 <div class="status-progress-bar-wrap" id="status-progress-bars"></div>
 <div class="status-top-user">
  <div class="av" id="status-viewer-av" style="width:36px;height:36px"><span>?</span></div>
  <div style="flex:1">
   <div id="status-viewer-name" style="font-weight:700;font-size:.95rem">Friend</div>
   <div id="status-viewer-time" style="font-size:.74rem;opacity:.8">Just now</div>
  </div>
  <button class="icon-btn" id="btn-close-status-viewer" style="color:#fff;font-size:1.4rem">✕</button>
 </div>
 <div class="status-viewer-content" id="status-viewer-body"></div>
 <div class="status-viewer-nav">
  <div class="status-nav-left" id="status-nav-prev"></div>
  <div class="status-nav-right" id="status-nav-next"></div>
 </div>
</div>

<!-- ========================================================
     MODAL: POST TEXT STATUS
     ======================================================== -->
<div class="modal-overlay" id="modal-text-status">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-text-status')">✕</button>
   <span>Post Text Status</span>
  </div>
  <form id="form-text-status" class="modal-body">
   <div id="status-preview-bg" style="background:linear-gradient(135deg, #0084ff, #005bb5);color:#fff;min-height:160px;border-radius:14px;padding:20px;display:flex;align-items:center;justify-content:center;text-align:center;font-size:1.3rem;font-weight:700">
    <textarea id="status-text-input" placeholder="Type a status update..." style="width:100%;height:100px;background:none;border:none;color:#fff;resize:none;text-align:center;font-size:1.2rem;font-weight:600" maxlength="280" required></textarea>
   </div>
   <div style="display:flex;gap:8px;align-items:center;justify-content:center;margin-top:6px">
    <span style="font-size:.8rem;color:var(--wa-mute)">Theme Color:</span>
    <button type="button" class="btn-round" style="width:28px;height:28px;background:linear-gradient(135deg, #0084ff, #005bb5)" onclick="setStatusBg('linear-gradient(135deg, #0084ff, #005bb5)')"></button>
    <button type="button" class="btn-round" style="width:28px;height:28px;background:linear-gradient(135deg, #7c3aed, #4f46e5)" onclick="setStatusBg('linear-gradient(135deg, #7c3aed, #4f46e5)')"></button>
    <button type="button" class="btn-round" style="width:28px;height:28px;background:linear-gradient(135deg, #ec4899, #be185d)" onclick="setStatusBg('linear-gradient(135deg, #ec4899, #be185d)')"></button>
    <button type="button" class="btn-round" style="width:28px;height:28px;background:linear-gradient(135deg, #059669, #047857)" onclick="setStatusBg('linear-gradient(135deg, #059669, #047857)')"></button>
    <button type="button" class="btn-round" style="width:28px;height:28px;background:#0f172a" onclick="setStatusBg('#0f172a')"></button>
   </div>
   <div class="modal-foot" style="margin:8px -22px -20px;padding-bottom:14px">
    <button type="button" class="btn-secondary" onclick="closeModal('modal-text-status')">Cancel</button>
    <button type="submit" class="btn-primary">Post Status</button>
   </div>
  </form>
 </div>
</div>

<!-- ========================================================
     MODAL: POST PHOTO STATUS
     ======================================================== -->
<div class="modal-overlay" id="modal-photo-status">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-photo-status')">✕</button>
   <span>Post Photo Status</span>
  </div>
  <form id="form-photo-status" class="modal-body">
   <div id="status-photo-preview-wrap" style="width:100%;height:200px;background:#f1f5f9;border-radius:12px;display:flex;align-items:center;justify-content:center;overflow:hidden;border:1px dashed var(--wa-line);cursor:pointer">
    <img id="status-photo-preview" src="" style="width:100%;height:100%;object-fit:cover;display:none">
    <div id="status-photo-prompt" style="text-align:center;color:var(--wa-mute);font-size:.88rem">
     <div style="font-size:2rem">📷</div>
     <div>Tap to choose a photo</div>
    </div>
   </div>
   <input class="input-field" id="status-photo-caption" placeholder="Add a caption..." maxlength="140">
   <div class="modal-foot" style="margin:8px -22px -20px;padding-bottom:14px">
    <button type="button" class="btn-secondary" onclick="closeModal('modal-photo-status')">Cancel</button>
    <button type="submit" class="btn-primary" id="btn-submit-photo-status" disabled>Post Photo Status</button>
   </div>
  </form>
 </div>
</div>

<!-- ========================================================
     MODAL: CREATE CHANNEL (Business Privilege)
     ======================================================== -->
<div class="modal-overlay" id="modal-create-channel">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-create-channel')">✕</button>
   <span>Create Business Channel</span>
  </div>
  <form id="form-create-channel" class="modal-body">
   <div style="display:flex;align-items:center;gap:12px">
    <div class="av lg group-av" id="channel-photo-prev" style="cursor:pointer" title="Pick Channel Logo">
     <span>📢</span>
    </div>
    <div style="flex:1">
     <button type="button" class="btn-secondary" id="btn-pick-channel-photo" style="font-size:.8rem;padding:6px 14px">Set Channel Logo</button>
     <div style="font-size:.74rem;color:var(--wa-mute);margin-top:4px">Visual badge for your subscribers</div>
    </div>
   </div>
   <label style="font-size:.84rem;color:var(--wa-mute)">Channel Name:</label>
   <input class="input-field" id="input-channel-name" placeholder="e.g. Acme Tech, Daily Updates, Store Deals" required maxlength="35" autocomplete="off">
   <label style="font-size:.84rem;color:var(--wa-mute)">Category:</label>
   <select class="input-field" id="select-channel-cat">
    <option value="Business & Retail">Business & Retail</option>
    <option value="Technology & Code">Technology & Code</option>
    <option value="News & Media">News & Media</option>
    <option value="Entertainment">Entertainment</option>
    <option value="Community & Education">Community & Education</option>
   </select>
   <label style="font-size:.84rem;color:var(--wa-mute)">Description (what will you share?):</label>
   <textarea class="input-field" id="input-channel-desc" placeholder="Describe your channel for prospective followers..." rows="3" maxlength="200"></textarea>
   <div class="modal-foot" style="margin:8px -22px -20px;padding-bottom:14px">
    <button type="button" class="btn-secondary" onclick="closeModal('modal-create-channel')">Cancel</button>
    <button type="submit" class="btn-primary">Create Channel</button>
   </div>
  </form>
 </div>
</div>

<!-- ========================================================
     MODAL: BUSINESS UPGRADE PROMPT
     ======================================================== -->
<div class="modal-overlay" id="modal-biz-upgrade">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-biz-upgrade')">✕</button>
   <span>Business Account Feature</span>
  </div>
  <div class="modal-body" style="text-align:center;gap:16px;padding:24px 22px">
   <div style="width:70px;height:70px;border-radius:50%;background:#eff6ff;color:#2563eb;display:grid;place-items:center;font-size:2.2rem;margin:0 auto">
    💼
   </div>
   <h3 style="font-size:1.2rem">Channels are for Business Accounts</h3>
   <p style="font-size:.88rem;color:var(--wa-mute);line-height:1.5">
    Broadcast Channels are exclusive to Business Accounts. Would you like to switch your account type to <b>Business</b> now? It takes 1 tap and is completely free!
   </p>
   <div style="display:flex;flex-direction:column;gap:8px;width:100%;margin-top:8px">
    <button class="btn-primary" id="btn-confirm-upgrade-biz" style="width:100%;padding:12px">Switch to Business & Create Channel</button>
    <button class="btn-secondary" onclick="closeModal('modal-biz-upgrade')" style="width:100%">Keep Personal Account</button>
   </div>
  </div>
 </div>
</div>

<!-- ========================================================
     MODAL: ADD FRIEND WITH LIVE AUTO-SUGGEST & VALIDATION
     ======================================================== -->
<div class="modal-overlay" id="modal-add-friend">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-add-friend')">✕</button>
   <span>New Chat / Add Contact</span>
  </div>
  <form id="form-add-friend" class="modal-body">
   <label style="font-size:.84rem;color:var(--wa-mute)">Search user by Walkie Talkie ID or Name:</label>
   <input class="input-field" id="input-friend-id" placeholder="Enter user ID (e.g. ECHO00, K8M9X2)" required maxlength="25" autocomplete="off">
   
   <!-- Real-time status feedback -->
   <div id="friend-search-feedback" style="font-size:.78rem;font-weight:600;color:var(--wa-mute);margin-top:-6px">
    Type an ID or select from matching directory below
   </div>

   <!-- Live Auto-Suggestions dropdown list -->
   <ul class="suggestions-box" id="friend-suggestions-list"></ul>

   <label style="font-size:.84rem;color:var(--wa-mute);margin-top:4px">Custom Name (only visible to you on this device):</label>
   <input class="input-field" id="input-friend-name" placeholder="Contact Nickname (optional)" maxlength="30" autocomplete="off">

   <div class="modal-foot" style="margin:8px -22px -20px;padding-bottom:14px">
    <button type="button" class="btn-secondary" onclick="closeModal('modal-add-friend')">Cancel</button>
    <button type="submit" class="btn-primary" id="btn-add-friend-submit" disabled>Add & Chat</button>
   </div>
  </form>
 </div>
</div>

<!-- ========================================================
     MODAL: NEW GROUP
     ======================================================== -->
<div class="modal-overlay" id="modal-new-group">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-new-group')">✕</button>
   <span>Create New Group</span>
  </div>
  <form id="form-new-group" class="modal-body">
   <div style="display:flex;align-items:center;gap:14px">
    <div class="av group-av lg" id="group-icon-prev" style="cursor:pointer" title="Choose group icon">
     <span>👥</span>
    </div>
    <div style="flex:1">
     <button type="button" class="btn-secondary" id="btn-group-photo" style="font-size:.8rem;padding:6px 14px">Set Group Photo</button>
     <div style="font-size:.74rem;color:var(--wa-mute);margin-top:4px">Optional icon for this group</div>
    </div>
   </div>
   <label style="font-size:.84rem;color:var(--wa-mute)">Group Subject / Name:</label>
   <input class="input-field" id="input-group-name" placeholder="e.g. Squad Talk, Work, Family" required maxlength="30" autocomplete="off">
   <label style="font-size:.84rem;color:var(--wa-mute)">Select Members to add:</label>
   <ul class="suggestions-box show" id="group-member-choices" style="max-height:160px"></ul>
   <div class="modal-foot" style="margin:8px -22px -20px;padding-bottom:14px">
    <button type="button" class="btn-secondary" onclick="closeModal('modal-new-group')">Cancel</button>
    <button type="submit" class="btn-primary">Create Group</button>
   </div>
  </form>
 </div>
</div>

<!-- ========================================================
     MODAL: CONTACT / GROUP INFO & RENAME
     ======================================================== -->
<div class="modal-overlay" id="modal-info">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-info')">✕</button>
   <span id="info-modal-title">Contact Info</span>
  </div>
  <div class="modal-body" style="align-items:center;text-align:center">
   <div class="av lg" id="info-av"><span>?</span></div>
   <h3 id="info-display-name" style="margin-top:6px;display:flex;align-items:center;gap:6px">Name</h3>
   <div id="info-subtext" style="font-size:.84rem;color:var(--wa-mute)">ID: ------</div>
   <div style="width:100%;border-top:1px solid var(--wa-line);padding-top:12px;margin-top:4px;display:flex;flex-direction:column;gap:8px;text-align:left">
    <label style="font-size:.84rem;font-weight:600;color:var(--wa-text)">Custom Name (only for you):</label>
    <div style="display:flex;gap:6px">
     <input class="input-field" id="info-custom-name" placeholder="Rename contact for yourself">
     <button class="btn-primary" id="btn-save-rename" style="padding:8px 16px;white-space:nowrap">Save</button>
    </div>
    <div style="font-size:.74rem;color:var(--wa-mute)">This custom name is saved locally and only seen by you on this device.</div>
   </div>
   <div id="info-group-members-box" style="display:none;width:100%;text-align:left;border-top:1px solid var(--wa-line);padding-top:10px">
    <div style="font-size:.84rem;font-weight:600;margin-bottom:6px">Members:</div>
    <ul class="suggestions-box show" id="info-group-members-list" style="max-height:120px"></ul>
   </div>
   <div style="width:100%;border-top:1px solid var(--wa-line);padding-top:12px;display:flex;justify-content:space-between;gap:8px">
    <button class="btn-danger" id="btn-block-contact">Block Contact</button>
    <button class="btn-danger" id="btn-delete-chat">Delete Chat</button>
   </div>
  </div>
 </div>
</div>

<!-- ========================================================
     MODAL: MY PROFILE & SETTINGS
     ======================================================== -->
<div class="modal-overlay" id="modal-settings">
 <div class="modal-card">
  <div class="modal-head">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-settings')">✕</button>
   <span>My Profile & Account</span>
  </div>
  <div class="modal-body" style="align-items:center;text-align:center">
   <div class="av lg my-av-box" id="settings-av-box" title="Click to change profile photo">
    <span id="settings-av-letter">U</span>
   </div>
   <div style="display:flex;gap:8px;margin-top:6px">
    <button class="btn-secondary" id="btn-change-my-photo" style="font-size:.8rem;padding:6px 14px">Change Photo</button>
    <button class="btn-danger" id="btn-remove-my-photo" style="font-size:.8rem;padding:6px 14px" hidden>Remove</button>
   </div>
   <div style="width:100%;text-align:left;display:flex;flex-direction:column;gap:12px;margin-top:10px">
    <div>
     <label style="font-size:.8rem;color:var(--wa-mute)">Your Display Name:</label>
     <div style="display:flex;gap:6px;margin-top:4px">
      <input class="input-field" id="settings-name-input" maxlength="24">
      <button class="btn-primary" id="btn-save-my-name" style="padding:6px 16px">Save</button>
     </div>
    </div>
    <div>
     <label style="font-size:.8rem;color:var(--wa-mute)">Account Type:</label>
     <div style="display:flex;gap:10px;margin-top:4px">
      <select class="input-field" id="settings-account-type">
       <option value="personal">👤 Personal Account</option>
       <option value="business">💼 Business Account (Can Create Channels)</option>
      </select>
     </div>
    </div>
    <div>
     <label style="font-size:.8rem;color:var(--wa-mute)">Your Walkie Talkie ID:</label>
     <div style="display:flex;gap:6px;align-items:center;margin-top:4px">
      <b id="settings-my-id" style="font-size:.92rem;letter-spacing:1px;background:var(--wa-sidebar);padding:8px 12px;border-radius:8px;flex:1">------</b>
      <button class="btn-secondary" id="btn-copy-my-id">Copy ID</button>
      <button class="btn-secondary" id="btn-set-custom-id" title="Set a custom ID">Custom ID</button>
     </div>
    </div>
    <div style="padding:10px;border-radius:10px;background:#f0fdf4;border:1px solid #bbf7d0;font-size:.8rem;color:#166534;display:flex;align-items:center;gap:6px">
     <span>✓</span> <span id="settings-auth-status">Verified Account</span>
    </div>
   </div>
  </div>
 </div>
</div>

<!-- ========================================================
     MODAL: WHATSAPP-STYLE REGISTRATION & OTP VERIFICATION
     ======================================================== -->
<div class="modal-overlay" id="modal-auth">
 <div class="modal-card">
  <div class="modal-head" style="justify-content:center">
   <span>Welcome to WalkieTalkie</span>
  </div>

  <!-- STEP 1: Account Creation & Details -->
  <form id="form-auth-step1" class="modal-body" style="text-align:center">
   <svg class="no-chat-logo" style="width:64px;height:64px;margin:0 auto" viewBox="0 0 64 64" fill="none">
    <rect width="64" height="64" rx="16" fill="url(#logoLg)"/>
    <path d="M18 20C18 16.7 20.7 14 24 14H40C43.3 14 46 16.7 46 20V34C46 37.3 43.3 40 40 40H30L22 46V40H24C20.7 40 18 37.3 18 34V20Z" fill="white"/>
    <path d="M26 27C26 25 28 23 32 23C36 23 38 25 38 27" stroke="#0084ff" stroke-width="2.6" stroke-linecap="round"/>
    <circle cx="32" cy="34" r="1.5" fill="#0084ff"/>
   </svg>
   <h3 style="font-size:1.15rem;font-weight:700">Create Your Account</h3>
   <p style="font-size:.84rem;color:var(--wa-mute);margin-top:-6px">
    Choose your username and account type with secure mobile/email verification.
   </p>

   <div style="text-align:left;display:flex;flex-direction:column;gap:12px;margin-top:6px">
    <div>
     <label style="font-size:.8rem;font-weight:600;color:var(--wa-text)">Unique Username:</label>
     <input class="input-field" id="auth-name" placeholder="e.g. Alex, Maya, TechCorp" required maxlength="24" autocomplete="off">
     <div id="auth-name-error" style="font-size:.75rem;font-weight:600;color:var(--wa-red);margin-top:3px;display:none">
      ❌ Username already taken! Please pick a different name.
     </div>
    </div>

    <div>
     <label style="font-size:.8rem;font-weight:600;color:var(--wa-text)">Account Type:</label>
     <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:4px">
      <label style="border:1.5px solid var(--wa-line);padding:10px;border-radius:10px;cursor:pointer;display:flex;align-items:center;gap:6px;font-size:.85rem;font-weight:600" id="lbl-type-personal">
       <input type="radio" name="auth-account-type" value="personal" checked>
       <span>👤 Personal</span>
      </label>
      <label style="border:1.5px solid var(--wa-line);padding:10px;border-radius:10px;cursor:pointer;display:flex;align-items:center;gap:6px;font-size:.85rem;font-weight:600" id="lbl-type-business">
       <input type="radio" name="auth-account-type" value="business">
       <span>💼 Business</span>
      </label>
     </div>
    </div>

    <div>
     <label style="font-size:.8rem;font-weight:600;color:var(--wa-text)">Mobile Number or Email Verification:</label>
     <div style="display:flex;gap:6px;margin-top:4px">
      <select class="input-field" id="auth-country-code" style="width:110px;flex:none">
       <option value="+1">+1 (US)</option>
       <option value="+91" selected>+91 (IN)</option>
       <option value="+44">+44 (UK)</option>
       <option value="+61">+61 (AU)</option>
       <option value="+971">+971 (AE)</option>
       <option value="email">📧 Email</option>
      </select>
      <input class="input-field" id="auth-contact-input" placeholder="Phone or email" required autocomplete="off">
     </div>
    </div>
   </div>

   <div class="modal-foot" style="margin:10px -22px -20px;padding-bottom:14px">
    <button type="submit" class="btn-primary" id="btn-auth-send-code" style="width:100%">Send Verification Code</button>
   </div>
  </form>

  <!-- STEP 2: 6-Digit OTP Verification Screen -->
  <form id="form-auth-step2" class="modal-body" style="display:none;text-align:center">
   <div style="font-size:2.4rem">🔐</div>
   <h3 style="font-size:1.15rem;font-weight:700">Enter Verification Code</h3>
   <p style="font-size:.84rem;color:var(--wa-mute);margin-top:-6px" id="auth-otp-target-label">
    We sent a 6-digit code to your mobile / email.
   </p>

   <div style="margin:14px 0">
    <input class="input-field" id="auth-otp-input" placeholder="• • • • • •" maxlength="6" style="text-align:center;font-size:1.8rem;letter-spacing:8px;font-weight:700" required autocomplete="off">
   </div>
   <div style="font-size:.76rem;color:var(--wa-mute)">
    Didn't get the code? <a href="#" id="auth-resend-link" style="color:var(--wa-teal);font-weight:600;text-decoration:none">Resend Code</a>
   </div>

   <div class="modal-foot" style="margin:12px -22px -20px;padding-bottom:14px">
    <button type="button" class="btn-secondary" id="btn-auth-back">Back</button>
    <button type="submit" class="btn-primary" style="flex:1">Verify & Continue</button>
   </div>
  </form>
 </div>
</div>

<!-- ========================================================
     SECRET ADMIN CONTROL PANEL (ID 20262026)
     ======================================================== -->
<div class="modal-overlay" id="modal-admin">
 <div class="modal-card">
  <div class="modal-head" style="background:#0f172a">
   <button class="icon-btn" style="color:#fff;margin-left:-8px" onclick="closeModal('modal-admin')">✕</button>
   <span>🛡️ Admin Command Center</span>
  </div>
  <div class="modal-body">
   <div style="background:#f8fafc;padding:10px 14px;border-radius:10px;font-size:.85rem">
    <b>Admin Status:</b> <span style="color:var(--wa-teal)">Active (ID 20262026)</span>
   </div>
   <div style="display:flex;flex-direction:column;gap:8px">
    <label style="font-size:.84rem;font-weight:700">📢 Global Broadcast Announcement</label>
    <div style="display:flex;gap:6px">
     <input class="input-field" id="admin-broadcast-input" placeholder="Broadcast alert to all connected users...">
     <button class="btn-primary" id="btn-admin-broadcast">Broadcast</button>
    </div>
   </div>
   <div style="display:flex;flex-direction:column;gap:8px">
    <label style="font-size:.84rem;font-weight:700">⚡ Connected Peers & Moderation</label>
    <ul class="suggestions-box show" id="admin-peers-list" style="max-height:160px"></ul>
   </div>
   <div style="border-top:1px solid var(--wa-line);padding-top:10px;display:flex;gap:8px;justify-content:space-between">
    <button class="btn-danger" id="btn-admin-wipe-all">Wipe All Room Chats</button>
    <button class="btn-secondary" onclick="closeModal('modal-admin')">Close</button>
   </div>
  </div>
 </div>
</div>

<!-- Real-time Push Notification for OTP -->
<div id="push-otp-banner">
 <span>📲</span>
 <div>
  <div style="font-size:.78rem;color:#94a3b8">WalkieTalkie Security Verification</div>
  <div style="font-size:.9rem">Your 6-digit code is: <span class="otp-pill" id="banner-otp-code">---</span></div>
 </div>
</div>

<!-- Hidden File Inputs -->
<input type="file" id="file-input-photo" accept="image/*" hidden>
<input type="file" id="input-chat-img" accept="image/*" multiple hidden>
<input type="file" id="input-chat-doc" accept="*/*" multiple hidden>
<input type="file" id="input-chat-cam" accept="image/*" capture="environment" hidden>
<input type="file" id="input-status-photo" accept="image/*" hidden>
<input type="file" id="input-channel-logo" accept="image/*" hidden>

<div id="toast" role="status"></div>

<script src="https://cdn.jsdelivr.net/npm/peerjs@1.5.4/dist/peerjs.min.js"></script>
<script>
(function(){
'use strict';
const $=s=>document.querySelector(s);
const $$=s=>document.querySelectorAll(s);
const ECHO='ECHO00',ALPHA='ABCDEFGHJKLMNPQRSTUVWXYZ23456789';
const _SECRET_ADMIN_ID='20262026';

const ls={
  get(k,d){try{const v=localStorage.getItem(k);return v?JSON.parse(v):d}catch(e){return d}},
  set(k,v){try{localStorage.setItem(k,JSON.stringify(v))}catch(e){}}
};

const genId=()=>{let s='';crypto.getRandomValues(new Uint8Array(6)).forEach(b=>s+=ALPHA[b%32]);return s};
const uid=()=>Date.now().toString(36)+Math.random().toString(36).slice(2,8);

function normId(s){
  if(!s)return '';
  return s.toUpperCase().trim().replace(/[^A-Z0-9\-]/g,'');
}

const fmtTime=t=>new Date(t).toLocaleTimeString([],{hour:'2-digit',minute:'2-digit'});
const fmtDateBadge=t=>{
  const d=new Date(t),now=new Date();
  if(d.toDateString()===now.toDateString())return 'TODAY';
  const yest=new Date(now);yest.setDate(now.getDate()-1);
  if(d.toDateString()===yest.toDateString())return 'YESTERDAY';
  return d.toLocaleDateString([],{month:'short',day:'numeric'});
};

const el=(t,c,x)=>{const e=document.createElement(t);if(c)e.className=c;if(x!=null)e.textContent=x;return e};

function getFileIcon(name){
  const ext=(name.split('.').pop()||'').toLowerCase();
  if(['pdf'].includes(ext)) return '📕';
  if(['doc','docx','txt','rtf','odt'].includes(ext)) return '📄';
  if(['xls','xlsx','csv'].includes(ext)) return '📊';
  if(['zip','rar','7z','tar','gz'].includes(ext)) return '📦';
  if(['mp3','wav','ogg','m4a','flac'].includes(ext)) return '🎵';
  if(['mp4','mov','mkv','webm'].includes(ext)) return '🎬';
  if(['js','html','css','json','py','cpp','c','java'].includes(ext)) return '💻';
  return '📁';
}

function formatFileSize(bytes){
  if(!bytes||bytes<1024) return (bytes||0)+' B';
  if(bytes<1048576) return (bytes/1024).toFixed(1)+' KB';
  return (bytes/1048576).toFixed(1)+' MB';
}

/* ---------- State ---------- */
let me=ls.get('wt_me',null);
let registeredAccounts=ls.get('wt_accounts',[
  {id:ECHO,name:'Echo Test',accountType:'business',category:'Testing Bot',verified:true},
  {id:'20262026',name:'Admin Support',accountType:'business',category:'System Official',verified:true}
]);

let contacts=ls.get('wt_contacts',null)||[
  {id:ECHO,name:'Echo Test',customName:'',photo:'',isGroup:false,accountType:'business'}
];

let groups=ls.get('wt_groups',{})||{};
let channels=ls.get('wt_channels',{})||{
  'TECH-UPDATES':{
    id:'TECH-UPDATES',name:'Tech & Gadgets',category:'Technology & Code',desc:'Daily tech news, product launches & tips',owner:ECHO,followers:[ECHO],photo:''
  },
  'OFFICIAL-ANNOUNCE':{
    id:'OFFICIAL-ANNOUNCE',name:'WalkieTalkie Official',category:'Business & Retail',desc:'Official feature announcements and release notes',owner:'20262026',followers:['20262026'],photo:''
  }
};

let statuses=ls.get('wt_statuses',{})||{};
let messages=ls.get('wt_msgs',{})||{};
let outbox=ls.get('wt_outbox',{})||{};
let blocked=new Set(ls.get('wt_blocked',[]));
let activeChatId=null;
let activeTab='chats';
let filterMode='all';

const save=()=>{
  ls.set('wt_contacts',contacts);
  ls.set('wt_groups',groups);
  ls.set('wt_channels',channels);
  ls.set('wt_statuses',statuses);
  ls.set('wt_msgs',messages);
  ls.set('wt_outbox',outbox);
  ls.set('wt_blocked',[...blocked]);
  ls.set('wt_accounts',registeredAccounts);
  if(me)ls.set('wt_me',me);
};

/* Secret Admin Verification */
function isAdmin(){
  return !!(me && (me.id === _SECRET_ADMIN_ID || me.secretAdmin));
}

/* Peer networking */
let peer=null,conns={},tried={};
let playingAud=null,toastT=null;

/* Image compressor */
function compressImage(file, maxDim=160, quality=0.82){
  return new Promise((resolve,reject)=>{
    if(!file||!file.type.startsWith('image/'))return reject('Not an image');
    const r=new FileReader();
    r.onload=e=>{
      const img=new Image();
      img.onload=()=>{
        const canvas=document.createElement('canvas');
        const size=Math.min(img.width,img.height);
        const sx=(img.width-size)/2,sy=(img.height-size)/2;
        canvas.width=maxDim;canvas.height=maxDim;
        const ctx=canvas.getContext('2d');
        ctx.drawImage(img,sx,sy,size,size,0,0,maxDim,maxDim);
        resolve(canvas.toDataURL('image/jpeg',quality));
      };
      img.onerror=()=>reject('Invalid image');
      img.src=e.target.result;
    };
    r.onerror=()=>reject('Read error');
    r.readAsDataURL(file);
  });
}

function optimizeChatImage(file, maxDim=1600, quality=0.85){
  return new Promise((resolve)=>{
    if(!file||!file.type.startsWith('image/')){
      const r=new FileReader();
      r.onload=e=>resolve(e.target.result);
      r.readAsDataURL(file);
      return;
    }
    const r=new FileReader();
    r.onload=e=>{
      const img=new Image();
      img.onload=()=>{
        let w=img.width, h=img.height;
        if(w>maxDim||h>maxDim){
          if(w>h){h=Math.round((h*maxDim)/w);w=maxDim}
          else{w=Math.round((w*maxDim)/h);h=maxDim}
        }
        const canvas=document.createElement('canvas');
        canvas.width=w;canvas.height=h;
        const ctx=canvas.getContext('2d');
        ctx.drawImage(img,0,0,w,h);
        resolve(canvas.toDataURL('image/jpeg',quality));
      };
      img.onerror=()=>resolve(e.target.result);
      img.src=e.target.result;
    };
    r.readAsDataURL(file);
  });
}

function setAvContent(avEl, photoUrl, fallbackText, isGroup=false){
  const oldImg=avEl.querySelector('img');
  if(oldImg)oldImg.remove();
  let span=avEl.querySelector('span');
  if(!span){span=el('span');avEl.append(span)}
  if(photoUrl){
    const img=el('img');img.src=photoUrl;img.alt='';
    avEl.prepend(img);
    span.hidden=true;
  }else{
    span.hidden=false;
    span.textContent=isGroup?'👥':(fallbackText||'?').slice(0,1).toUpperCase();
  }
}

function getContact(id){return contacts.find(c=>c.id===id)}
function displayName(id){
  if(me && id===me.id)return 'You';
  if(groups[id])return groups[id].name;
  if(channels[id])return channels[id].name;
  const c=getContact(id);
  if(c){
    if(c.customName&&c.customName.trim())return c.customName.trim();
    if(c.name)return c.name;
  }
  const acc=registeredAccounts.find(a=>a.id===id);
  if(acc)return acc.name;
  return id;
}

function displayPhoto(id){
  if(me && id===me.id)return me.photo||'';
  if(groups[id])return groups[id].photo||'';
  if(channels[id])return channels[id].photo||'';
  const c=getContact(id);
  return (c&&c.photo)||'';
}

function isContactOnline(id){
  if(id===ECHO)return true;
  if(channels[id])return true;
  if(groups[id]){
    return groups[id].members.some(m=>m!==me.id&&conns[m]&&conns[m].open);
  }
  return !!(conns[id]&&conns[id].open&&Date.now()-conns[id].pong<15000);
}

/* Audio & Toast */
function toast(t){
  const e=$('#toast');e.textContent=t;e.style.display='block';
  clearTimeout(toastT);toastT=setTimeout(()=>e.style.display='none',3200);
}
let actx;
function beep(f,d,delay=0,type='sine',v=.06){
  try{
    actx=actx||new(window.AudioContext||window.webkitAudioContext)();
    if(actx.state==='suspended')actx.resume();
    const o=actx.createOscillator(),g=actx.createGain();o.type=type;o.frequency.value=f;g.gain.value=v;
    o.connect(g);g.connect(actx.destination);const t=actx.currentTime+delay;o.start(t);o.stop(t+d);
  }catch(e){}
}
const playSentChime=()=>beep(900,.04,0,'sine',.04);
const playRecvChime=()=>{beep(800,.05,0,'sine',.05);beep(1200,.08,.06,'sine',.05)};
const squelch=()=>beep(650,.07,0,'square',.03);

let ringOscInterval=null;
function startRingtone(){
  stopRingtone();
  ringOscInterval=setInterval(()=>{
    beep(440,.3,0,'sine',.08);beep(480,.3,.05,'sine',.08);
  },2000);
}
function stopRingtone(){
  if(ringOscInterval){clearInterval(ringOscInterval);ringOscInterval=null}
}

/* ---------- PeerJS Setup ---------- */
function startPeer(){
  if(!me||typeof Peer==='undefined')return;
  peer=new Peer('wtalk-'+me.id);
  peer.on('open',()=>{
    flushAllOutbox();
  });
  peer.on('connection',c=>{
    const rid=c.peer.replace('wtalk-','');
    if(blocked.has(rid)){c.on('open',()=>c.close());return}
    setupConn(c);
  });
  peer.on('call',mediaConn=>{
    handleIncomingMediaCall(mediaConn);
  });
  peer.on('disconnected',()=>{try{peer.reconnect()}catch(e){}});
  peer.on('error',e=>{
    if(e.type==='unavailable-id')toast('ID '+me.id+' already connected');
  });
}

function connectTo(id){
  if(id===ECHO||!peer||!peer.open||blocked.has(id)||(conns[id]&&conns[id].open))return;
  if(Date.now()-(tried[id]||0)<4000)return;
  tried[id]=Date.now();
  setupConn(peer.connect('wtalk-'+id,{reliable:true}));
}

function setupConn(c){
  const rid=c.peer.replace('wtalk-','');
  c.on('open',()=>{
    c.pong=Date.now();conns[rid]=c;
    c.send({
      t:'hello',
      name:me.name,
      photo:me.photo||'',
      customId:me.id,
      accountType:me.accountType||'personal'
    });
    flushOutbox(rid);
    refreshUI();
  });
  c.on('data',d=>onData(rid,d));
  const gone=()=>{if(conns[rid]===c){delete conns[rid]}refreshUI()};
  c.on('close',gone);c.on('error',gone);
}

function sendRaw(id,o){
  const c=conns[id];
  if(c&&c.open){try{c.send(o);return true}catch(e){}}
  return false;
}

setInterval(()=>{
  if(!peer||!peer.open)return;
  Object.keys(conns).forEach(id=>sendRaw(id,{t:'ping',ts:Date.now()}));
  contacts.slice(0,30).forEach(c=>connectTo(c.id));
  Object.values(groups).forEach(g=>g.members.forEach(m=>m!==me.id&&connectTo(m)));
  refreshUI();
},4000);

/* ---------- Receive Protocol ---------- */
function onData(rid,d){
  if(!d||!d.t||blocked.has(rid))return;
  const c=conns[rid];

  if(d.t==='hello'){
    if(c){c.nm=d.name;c.photo=d.photo}
    let contact=getContact(rid);
    if(!contact){
      contact={id:rid,name:d.name||rid,customName:'',photo:d.photo||'',isGroup:false,accountType:d.accountType||'personal'};
      contacts.push(contact);
    }else{
      if(d.name)contact.name=d.name;
      if(d.photo!==undefined)contact.photo=d.photo;
      if(d.accountType)contact.accountType=d.accountType;
    }
    // Update accounts directory
    if(!registeredAccounts.some(a=>a.id===rid)){
      registeredAccounts.push({id:rid,name:d.name||rid,accountType:d.accountType||'personal',verified:true});
    }
    save();
    flushOutbox(rid);
    refreshUI();
  }else if(d.t==='ping'){
    sendRaw(rid,{t:'pong',ts:d.ts});
  }else if(d.t==='pong'&&c){
    c.pong=Date.now();
  }else if(d.t==='msg'){
    handleIncomingMessage(rid,d);
  }else if(d.t==='voice'){
    handleIncomingVoice(rid,d);
  }else if(d.t==='ack'){
    handleAck(d.mid,d.status||'delivered');
  }else if(d.t==='channel_post'){
    handleChannelPost(d);
  }else if(d.t==='status_post'){
    handleStatusPost(rid,d);
  }else if(d.t==='call_declined'){
    handleCallDeclined(rid);
  }else if(d.t==='admin_broadcast'){
    $('#admin-announcement-text').textContent=d.text;
    $('#admin-announcement-bar').style.display='flex';
    beep(1000,.1);beep(1400,.15,.1);
  }else if(d.t==='admin_kick'){
    toast('You were disconnected by the Admin');
    if(conns[rid])conns[rid].close();
  }
}

/* ---------- Messages & Offline Outbox ---------- */
function getChatMessages(chatId){
  if(!messages[chatId])messages[chatId]=[];
  return messages[chatId];
}

function addChatMessage(chatId,msg){
  const list=getChatMessages(chatId);
  list.push(msg);
  if(list.length>300)messages[chatId]=list.slice(-300);
  save();
}

function queueOutbox(peerId,payload){
  if(!outbox[peerId])outbox[peerId]=[];
  outbox[peerId].push(payload);
  save();
}

function flushOutbox(peerId){
  if(!outbox[peerId]||!outbox[peerId].length)return;
  const pending=[...outbox[peerId]];
  outbox[peerId]=[];
  save();
  pending.forEach(item=>{
    const sent=sendRaw(peerId,item);
    if(!sent){
      queueOutbox(peerId,item);
    }else{
      updateMessageStatus(item.mid,'sent');
    }
  });
}

function flushAllOutbox(){
  Object.keys(outbox).forEach(peerId=>{
    if(conns[peerId]&&conns[peerId].open)flushOutbox(peerId);
  });
}

function updateMessageStatus(mid,newStatus){
  let changed=false;
  Object.keys(messages).forEach(k=>{
    messages[k].forEach(m=>{
      if(m.id===mid){
        m.status=newStatus;changed=true;
      }
    });
  });
  if(changed){save();renderMessages()}
}

function handleAck(mid,status){
  updateMessageStatus(mid,status);
}

function handleIncomingMessage(senderId,d){
  const chatId=d.groupId||senderId;
  const msg={
    id:d.mid||uid(),
    from:senderId,
    name:d.name||displayName(senderId),
    photo:d.photo||displayPhoto(senderId),
    text:d.text||'',
    fileData:d.fileData||null,
    fileName:d.fileName||null,
    fileSize:d.fileSize||null,
    fileType:d.fileType||null,
    ts:d.ts||Date.now(),
    status:'delivered',
    isVoice:false,
    groupId:d.groupId||null
  };
  addChatMessage(chatId,msg);

  if(activeChatId===chatId){
    sendRaw(senderId,{t:'ack',mid:msg.id,status:'read'});
    msg.status='read';
  }else{
    sendRaw(senderId,{t:'ack',mid:msg.id,status:'delivered'});
  }

  playRecvChime();
  if(activeChatId===chatId){
    renderMessages();
  }else{
    const previewTxt=msg.fileType==='image'?'📷 Photo':(msg.fileType==='file'?'📄 '+msg.fileName:d.text);
    toast('💬 '+displayName(senderId)+': '+previewTxt);
  }
  refreshUI();
}

function handleIncomingVoice(senderId,d){
  const chatId=d.groupId||senderId;
  const blob=new Blob([d.buf],{type:d.mime});
  const blobUrl=URL.createObjectURL(blob);
  const msg={
    id:d.mid||uid(),
    from:senderId,
    name:d.name||displayName(senderId),
    photo:d.photo||displayPhoto(senderId),
    text:'',
    audioBlobUrl:blobUrl,
    dur:d.dur||1,
    ts:d.ts||Date.now(),
    status:'delivered',
    isVoice:true,
    groupId:d.groupId||null
  };
  addChatMessage(chatId,msg);

  if(activeChatId===chatId){
    sendRaw(senderId,{t:'ack',mid:msg.id,status:'read'});
    msg.status='read';
    renderMessages();
  }else{
    sendRaw(senderId,{t:'ack',mid:msg.id,status:'delivered'});
    toast('🎙️ Voice note from '+displayName(senderId));
  }
  playRecvChime();
  refreshUI();
}

/* Dispatch payload */
function dispatchPayload(payload, localMsg){
  const isGrp=!!groups[activeChatId];
  if(isGrp){
    const group=groups[activeChatId];
    group.members.forEach(memberId=>{
      if(memberId===me.id)return;
      const sent=sendRaw(memberId,payload);
      if(!sent)queueOutbox(memberId,payload);
    });
    localMsg.status='sent';
    renderMessages();
  }else{
    const sent=sendRaw(activeChatId,payload);
    if(sent){
      localMsg.status='sent';
    }else{
      queueOutbox(activeChatId,payload);
      localMsg.status='pending';
    }
    renderMessages();
  }
}

/* Send a message */
function sendMessage(text){
  if(!activeChatId||!text.trim())return;
  const mid=uid();
  const isGrp=!!groups[activeChatId];
  const isChan=!!channels[activeChatId];

  if(isChan){
    postToChannel(activeChatId, text);
    return;
  }

  const msg={
    id:mid,
    from:me.id,
    name:me.name,
    photo:me.photo||'',
    text:text,
    ts:Date.now(),
    status:'pending',
    isVoice:false,
    groupId:isGrp?activeChatId:null
  };

  addChatMessage(activeChatId,msg);
  renderMessages();
  playSentChime();

  if(activeChatId===ECHO){
    msg.status='delivered';
    setTimeout(()=>{
      msg.status='read';
      renderMessages();
      const reply={
        id:uid(),
        from:ECHO,
        name:'Echo Test',
        photo:'',
        text:'Echo: '+text,
        ts:Date.now(),
        status:'delivered',
        isVoice:false,
        groupId:null
      };
      addChatMessage(ECHO,reply);
      renderMessages();
      playRecvChime();
    },600);
    return;
  }

  const payload={
    t:'msg',mid,text,name:me.name,photo:me.photo||'',ts:msg.ts,groupId:isGrp?activeChatId:null
  };
  dispatchPayload(payload,msg);
}

/* Send File or Image */
async function sendFileAttachment(file, caption=''){
  if(!activeChatId||!file)return;
  const isImg=file.type.startsWith('image/');
  const mid=uid();
  const isGrp=!!groups[activeChatId];
  const dataUrl=await optimizeChatImage(file);

  const msg={
    id:mid,
    from:me.id,
    name:me.name,
    photo:me.photo||'',
    text:caption,
    fileData:dataUrl,
    fileName:file.name,
    fileSize:file.size,
    fileType:isImg?'image':'file',
    ts:Date.now(),
    status:'pending',
    isVoice:false,
    groupId:isGrp?activeChatId:null
  };

  addChatMessage(activeChatId,msg);
  renderMessages();
  playSentChime();

  if(activeChatId===ECHO){
    msg.status='delivered';
    setTimeout(()=>{
      msg.status='read';
      renderMessages();
      const reply={
        id:uid(),
        from:ECHO,
        name:'Echo Test',
        photo:'',
        text:'Echo received your '+(isImg?'photo:':'file:')+' '+file.name,
        fileData:dataUrl,
        fileName:file.name,
        fileSize:file.size,
        fileType:msg.fileType,
        ts:Date.now(),
        status:'delivered',
        isVoice:false,
        groupId:null
      };
      addChatMessage(ECHO,reply);
      renderMessages();
      playRecvChime();
    },700);
    return;
  }

  const payload={
    t:'msg',mid,text:caption,fileData:dataUrl,fileName:file.name,fileSize:file.size,fileType:msg.fileType,name:me.name,photo:me.photo||'',ts:msg.ts,groupId:isGrp?activeChatId:null
  };
  dispatchPayload(payload,msg);
}

/* Send voice note transmission */
function sendVoiceTransmission(blob,dur){
  if(!activeChatId)return;
  const mid=uid();
  const blobUrl=URL.createObjectURL(blob);
  const isGrp=!!groups[activeChatId];

  const msg={
    id:mid,
    from:me.id,
    name:me.name,
    photo:me.photo||'',
    text:'',
    audioBlobUrl:blobUrl,
    dur:dur,
    ts:Date.now(),
    status:'pending',
    isVoice:true,
    groupId:isGrp?activeChatId:null
  };

  addChatMessage(activeChatId,msg);
  renderMessages();
  playSentChime();

  if(activeChatId===ECHO){
    msg.status='delivered';
    setTimeout(()=>{
      msg.status='read';
      renderMessages();
      const reply={
        id:uid(),
        from:ECHO,
        name:'Echo Test',
        photo:'',
        text:'',
        audioBlobUrl:blobUrl,
        dur:dur,
        ts:Date.now(),
        status:'delivered',
        isVoice:true,
        groupId:null
      };
      addChatMessage(ECHO,reply);
      renderMessages();
      playRecvChime();
    },600);
    return;
  }

  blob.arrayBuffer().then(buf=>{
    const payload={
      t:'voice',mid,buf,mime:blob.type,dur,name:me.name,photo:me.photo||'',ts:msg.ts,groupId:isGrp?activeChatId:null
    };
    dispatchPayload(payload,msg);
  });
}

/* ========================================================
   WHATSAPP CHANNELS (Business Account Broadcast)
   ======================================================== */
function renderChannelsList(){
  const ul=$('#channels-feed-list');
  ul.innerHTML='';
  const chanArr=Object.values(channels);
  if(!chanArr.length){
    ul.append(el('li','','No channels yet. Create one!'));
    return;
  }

  chanArr.forEach(ch=>{
    const li=el('li');
    li.onclick=()=>openChat(ch.id);

    const av=el('div','av group-av');
    setAvContent(av,ch.photo,ch.name,true);

    const info=el('div','chat-info');
    const top=el('div','chat-top-row');
    const name=el('div','chat-name',ch.name);
    const badge=el('span','biz-badge','📢 CHANNEL');
    name.append(badge);

    const cat=el('div','chat-snippet',ch.category+' · '+ch.desc);
    top.append(name);
    info.append(top,cat);

    const isFollowing=(ch.followers||[]).includes(me.id);
    const flwBtn=el('button','channel-btn-follow'+(isFollowing?' following':''));
    flwBtn.textContent=isFollowing?'Following':'Follow';
    flwBtn.onclick=e=>{
      e.stopPropagation();
      toggleFollowChannel(ch.id);
    };

    li.append(av,info,flwBtn);
    ul.append(li);
  });
}

function toggleFollowChannel(cid){
  const ch=channels[cid];
  if(!ch)return;
  if(!ch.followers)ch.followers=[];
  const idx=ch.followers.indexOf(me.id);
  if(idx===-1){
    ch.followers.push(me.id);
    toast('Followed '+ch.name);
  }else{
    ch.followers.splice(idx,1);
    toast('Unfollowed '+ch.name);
  }
  save();
  renderChannelsList();
}

function postToChannel(cid, text){
  const ch=channels[cid];
  if(!ch)return;
  if(ch.owner!==me.id){
    return toast('Only channel admin can broadcast to this channel');
  }
  const mid=uid();
  const msg={
    id:mid,
    from:me.id,
    name:ch.name,
    photo:ch.photo||'',
    text:text,
    ts:Date.now(),
    status:'delivered',
    isVoice:false,
    isChannel:true,
    groupId:cid
  };
  addChatMessage(cid,msg);
  renderMessages();
  playSentChime();

  // Broadcast to all connected peers
  Object.keys(conns).forEach(rid=>{
    sendRaw(rid,{t:'channel_post',cid,msg});
  });
}

function handleChannelPost(d){
  if(!channels[d.cid])return;
  addChatMessage(d.cid,d.msg);
  if(activeChatId===d.cid){
    renderMessages();
    playRecvChime();
  }else{
    toast('📢 '+channels[d.cid].name+': '+d.msg.text);
  }
  refreshUI();
}

window.reactChannel=function(emoji){
  toast('Reacted '+emoji+' to channel update!');
  playSentChime();
};

/* ========================================================
   WHATSAPP STATUS / STORIES
   ======================================================== */
function renderStatusList(){
  const myStatusObj=statuses[me.id];
  if(myStatusObj&&myStatusObj.items&&myStatusObj.items.length){
    $('#my-status-sub').textContent=fmtTime(myStatusObj.items[myStatusObj.items.length-1].ts)+' · '+myStatusObj.items.length+' updates';
  }else{
    $('#my-status-sub').textContent='Tap to add status update';
  }
  setAvContent($('#my-status-av'),me.photo,me.name);

  const ul=$('#status-feed-list');
  ul.innerHTML='';
  let hasOtherStatus=false;

  Object.keys(statuses).forEach(uid=>{
    if(uid===me.id)return;
    const st=statuses[uid];
    if(!st||!st.items||!st.items.length)return;
    hasOtherStatus=true;

    const li=el('li');
    li.onclick=()=>viewStatus(uid);

    const ring=el('div','status-ring'+(st.viewed?' viewed':''));
    const av=el('div','av');
    setAvContent(av,displayPhoto(uid),displayName(uid));
    ring.append(av);

    const info=el('div','chat-info');
    const nm=el('div','chat-name',displayName(uid));
    const tm=el('div','chat-snippet',fmtTime(st.items[st.items.length-1].ts));
    info.append(nm,tm);

    li.append(ring,info);
    ul.append(li);
  });

  if(!hasOtherStatus){
    ul.append(el('li','','No recent status updates from friends'));
  }
}

let activeViewerUid=null,activeViewerIdx=0,statusTimer=null;

function viewStatus(uid){
  const st=statuses[uid];
  if(!st||!st.items||!st.items.length)return;
  st.viewed=true;
  save();
  renderStatusList();

  activeViewerUid=uid;
  activeViewerIdx=0;
  $('#status-viewer').classList.add('show');
  displayStatusItem();
}

function displayStatusItem(){
  clearTimeout(statusTimer);
  const st=statuses[activeViewerUid];
  if(!st||activeViewerIdx>=st.items.length){
    closeStatusViewer();
    return;
  }
  const item=st.items[activeViewerIdx];

  setAvContent($('#status-viewer-av'),displayPhoto(activeViewerUid),displayName(activeViewerUid));
  $('#status-viewer-name').textContent=displayName(activeViewerUid);
  $('#status-viewer-time').textContent=fmtTime(item.ts);

  // Setup Progress Bars
  const pWrap=$('#status-progress-bars');
  pWrap.innerHTML='';
  st.items.forEach((_,i)=>{
    const tr=el('div','status-seg-track');
    const fi=el('div','status-seg-fill');
    if(i<activeViewerIdx) fi.classList.add('done');
    tr.append(fi);
    pWrap.append(tr);
  });

  // Display content
  const body=$('#status-viewer-body');
  body.innerHTML='';
  if(item.type==='photo'){
    const img=el('img','status-img-slide');
    img.src=item.data;
    body.append(img);
    if(item.caption){
      const cap=el('div','',{style:'position:absolute;bottom:20px;background:rgba(0,0,0,.6);padding:8px 16px;border-radius:16px;font-size:1.1rem;color:#fff'});
      cap.textContent=item.caption;
      body.append(cap);
    }
  }else{
    const txt=el('div','status-text-slide',item.text);
    txt.style.background=item.bg||'#0084ff';
    body.append(txt);
  }

  // Animate active segment
  const activeFill=pWrap.children[activeViewerIdx].querySelector('.status-seg-fill');
  setTimeout(()=>{
    if(activeFill)activeFill.style.width='100%';
  },20);

  statusTimer=setTimeout(()=>{
    activeViewerIdx++;
    displayStatusItem();
  },5000);
}

function closeStatusViewer(){
  clearTimeout(statusTimer);
  $('#status-viewer').classList.remove('show');
}
$('#btn-close-status-viewer').onclick=closeStatusViewer;
$('#status-nav-next').onclick=()=>{
  clearTimeout(statusTimer);
  activeViewerIdx++;
  displayStatusItem();
};
$('#status-nav-prev').onclick=()=>{
  clearTimeout(statusTimer);
  if(activeViewerIdx>0)activeViewerIdx--;
  displayStatusItem();
};

window.setStatusBg=function(bg){
  $('#status-preview-bg').style.background=bg;
};

/* Post status item */
function addStatusItem(item){
  if(!statuses[me.id])statuses[me.id]={items:[],viewed:true};
  statuses[me.id].items.push(item);
  save();
  renderStatusList();
  toast('Status posted!');

  // Broadcast status to connected peers
  Object.keys(conns).forEach(id=>{
    sendRaw(id,{t:'status_post',item});
  });
}

function handleStatusPost(rid,d){
  if(!statuses[rid])statuses[rid]={items:[],viewed:false};
  statuses[rid].items.push(d.item);
  statuses[rid].viewed=false;
  save();
  renderStatusList();
  $('#status-badge-dot').hidden=false;
}

$('#my-status-card').onclick=()=>{
  if(statuses[me.id]&&statuses[me.id].items&&statuses[me.id].items.length){
    viewStatus(me.id);
  }else{
    openModal('modal-text-status');
  }
};
$('#btn-post-text-status').onclick=()=>openModal('modal-text-status');
$('#btn-post-photo-status').onclick=()=>openModal('modal-photo-status');

$('#form-text-status').onsubmit=e=>{
  e.preventDefault();
  const text=$('#status-text-input').value.trim();
  if(!text)return;
  const bg=$('#status-preview-bg').style.background;
  addStatusItem({type:'text',text,bg,ts:Date.now()});
  closeModal('modal-text-status');
  $('#status-text-input').value='';
};

let tempStatusPhotoData='';
$('#status-photo-preview-wrap').onclick=()=>$('#input-status-photo').click();
$('#input-status-photo').onchange=async e=>{
  if(!e.target.files||!e.target.files[0])return;
  tempStatusPhotoData=await optimizeChatImage(e.target.files[0],1200);
  $('#status-photo-preview').src=tempStatusPhotoData;
  $('#status-photo-preview').style.display='block';
  $('#status-photo-prompt').style.display='none';
  $('#btn-submit-photo-status').disabled=false;
};

$('#form-photo-status').onsubmit=e=>{
  e.preventDefault();
  if(!tempStatusPhotoData)return;
  const caption=$('#status-photo-caption').value.trim();
  addStatusItem({type:'photo',data:tempStatusPhotoData,caption,ts:Date.now()});
  closeModal('modal-photo-status');
  tempStatusPhotoData='';
  $('#status-photo-preview').style.display='none';
  $('#status-photo-prompt').style.display='block';
  $('#status-photo-caption').value='';
  $('#btn-submit-photo-status').disabled=true;
};

/* ========================================================
   CHATS & RENDERING
   ======================================================== */
function renderChatsList(){
  const ul=$('#chats-list');
  ul.innerHTML='';
  const q=$('#search-input').value.toLowerCase().trim();

  let list=[];
  contacts.forEach(c=>{
    if(c.id===me.id)return;
    list.push({id:c.id,name:displayName(c.id),isGroup:false,photo:displayPhoto(c.id),accountType:c.accountType||'personal'});
  });
  Object.values(groups).forEach(g=>{
    list.push({id:g.id,name:g.name,isGroup:true,photo:g.photo||''});
  });

  list.sort((a,b)=>{
    const ma=messages[a.id]||[], mb=messages[b.id]||[];
    const ta=ma.length?ma[ma.length-1].ts:0;
    const tb=mb.length?mb[mb.length-1].ts:0;
    return tb-ta;
  });

  if(filterMode==='unread'){
    list=list.filter(x=>{
      const ms=messages[x.id]||[];
      return ms.some(m=>m.from!==me.id&&m.status!=='read');
    });
  }else if(filterMode==='groups'){
    list=list.filter(x=>x.isGroup);
  }

  if(q){
    list=list.filter(x=>x.name.toLowerCase().includes(q)||x.id.toLowerCase().includes(q));
  }

  if(!list.length){
    ul.append(el('li','','No chats match your search'));
    return;
  }

  list.forEach(item=>{
    const li=el('li');
    if(item.id===activeChatId)li.classList.add('active');
    li.onclick=()=>openChat(item.id);

    const av=el('div','av'+(item.isGroup?' group-av':''));
    setAvContent(av,item.photo,item.name,item.isGroup);

    if(!item.isGroup){
      const dot=el('span','dot');
      if(isContactOnline(item.id))dot.classList.add('on');
      av.append(dot);
    }

    const info=el('div','chat-info');
    const top=el('div','chat-top-row');
    const nm=el('div','chat-name');
    nm.textContent=item.name;

    if(item.accountType==='business'){
      const b=el('span','biz-badge','💼');
      b.title='Verified Business';
      nm.append(b);
    }

    const ms=messages[item.id]||[];
    const lastMsg=ms.length?ms[ms.length-1]:null;

    const tm=el('div','chat-time',lastMsg?fmtTime(lastMsg.ts):'');
    top.append(nm,tm);

    const bot=el('div','chat-bottom-row');
    const snip=el('div','chat-snippet');
    if(lastMsg){
      if(lastMsg.isVoice) snip.textContent='🎙️ Voice note';
      else if(lastMsg.fileType==='image') snip.textContent='📷 Photo';
      else if(lastMsg.fileType==='file') snip.textContent='📄 '+lastMsg.fileName;
      else snip.textContent=lastMsg.text;
    }else{
      snip.textContent=item.isGroup?'Group created':'Tap to chat';
    }

    bot.append(snip);

    const unreadCount=ms.filter(m=>m.from!==me.id&&m.status!=='read').length;
    if(unreadCount>0){
      const badge=el('span','chat-badge',String(unreadCount));
      bot.append(badge);
    }

    info.append(top,bot);
    li.append(av,info);
    ul.append(li);
  });
}

function openChat(id){
  activeChatId=id;
  $('#app').classList.add('in-chat');
  $('#no-chat').style.display='none';
  $('#chat-pane').style.display='flex';

  const isChan=!!channels[id];
  const isGrp=!!groups[id];

  setAvContent($('#header-av'),displayPhoto(id),displayName(id),isGrp||isChan);
  $('#chat-title').textContent=displayName(id);

  if(isChan){
    $('#chat-subtitle').textContent=channels[id].category+' · Broadcast';
    $('#chat-header-acts').style.display='none';
    if(channels[id].owner!==me.id){
      $('#chat-input-bar').style.display='none';
      $('#channel-react-bar').style.display='flex';
    }else{
      $('#chat-input-bar').style.display='flex';
      $('#channel-react-bar').style.display='none';
    }
  }else{
    $('#chat-header-acts').style.display='flex';
    $('#chat-input-bar').style.display='flex';
    $('#channel-react-bar').style.display='none';
    if(isGrp){
      $('#chat-subtitle').textContent=groups[id].members.length+' members';
    }else{
      $('#chat-subtitle').textContent=isContactOnline(id)?'Online':'Offline · Messages will queue';
    }
  }

  // Mark all unread messages as read
  const ms=messages[id]||[];
  let changed=false;
  ms.forEach(m=>{
    if(m.from!==me.id&&m.status!=='read'){
      m.status='read';
      changed=true;
      sendRaw(m.from,{t:'ack',mid:m.id,status:'read'});
    }
  });
  if(changed)save();

  renderMessages();
  renderChatsList();
  connectTo(id);
}

function renderMessages(){
  const cont=$('#messages-container');
  cont.innerHTML='';
  if(!activeChatId)return;

  const ms=getChatMessages(activeChatId);
  const isGrp=!!groups[activeChatId];
  let lastDateBadge='';

  ms.forEach(m=>{
    const dBadge=fmtDateBadge(m.ts);
    if(dBadge!==lastDateBadge){
      cont.append(el('div','msg-date-badge',dBadge));
      lastDateBadge=dBadge;
    }

    const isMe=m.from===me.id;
    const row=el('div','msg-row '+(isMe?'me':'them'));
    const bubble=el('div','msg-bubble');

    if(!isMe&&isGrp){
      const sender=el('div','msg-sender');
      sender.textContent=displayName(m.from);
      bubble.append(sender);
    }

    if(m.fileType==='image'&&m.fileData){
      const img=el('img','chat-img-preview');
      img.src=m.fileData;
      img.onclick=()=>openImageLightbox(m.fileData,m.fileName||'photo.jpg');
      bubble.append(img);
      if(m.text)bubble.append(el('div','msg-content',m.text));
    }else if(m.fileType==='file'&&m.fileData){
      const docCard=el('div','chat-doc-card');
      const icon=el('div','chat-doc-icon',getFileIcon(m.fileName||''));
      const docInfo=el('div','chat-doc-info');
      const docName=el('div','chat-doc-name',m.fileName||'Document');
      const docSize=el('div','chat-doc-size',formatFileSize(m.fileSize));
      docInfo.append(docName,docSize);
      const dlBtn=el('a','chat-doc-dl','📥');
      dlBtn.href=m.fileData;
      dlBtn.download=m.fileName||'download';
      docCard.append(icon,docInfo,dlBtn);
      bubble.append(docCard);
      if(m.text)bubble.append(el('div','msg-content',m.text));
    }else if(m.isVoice){
      const vn=el('div','vn-player');
      const playBtn=el('button','vn-btn','▶');
      playBtn.onclick=()=>{
        if(playingAud){playingAud.pause();playingAud=null}
        const a=new Audio(m.audioBlobUrl);
        playingAud=a;
        playBtn.textContent='⏸';
        a.onended=()=>{playBtn.textContent='▶';playingAud=null};
        a.onerror=()=>{playBtn.textContent='▶';playingAud=null};
        a.play().catch(()=>{playBtn.textContent='▶'});
      };
      const wave=el('div','vn-wave');
      for(let i=0;i<18;i++){
        const b=el('div','vn-bar');
        b.style.height=(6+Math.sin(i*1.2)*12)+'px';
        wave.append(b);
      }
      const dur=el('div','vn-dur',Math.round(m.dur)+'s');
      vn.append(playBtn,wave,dur);
      bubble.append(vn);
    }else{
      bubble.append(el('div','msg-content',m.text));
    }

    const foot=el('div','msg-foot');
    foot.append(el('span','',fmtTime(m.ts)));

    if(isMe){
      const tickSpan=el('span','tick');
      if(m.status==='pending'){
        tickSpan.className='tick pending';tickSpan.textContent='🕒';
      }else if(m.status==='sent'){
        tickSpan.className='tick sent';tickSpan.textContent='✓';
      }else if(m.status==='delivered'){
        tickSpan.className='tick delivered';tickSpan.textContent='✓✓';
      }else if(m.status==='read'){
        tickSpan.className='tick read';tickSpan.textContent='✓✓';
      }
      foot.append(tickSpan);
    }
    bubble.append(foot);
    row.append(bubble);
    cont.append(row);
  });

  cont.scrollTop=cont.scrollHeight;
}

/* Lightbox */
function openImageLightbox(src,name){
  $('#lightbox-img').src=src;
  const dl=$('#lightbox-dl-btn');
  dl.href=src;
  dl.download=name||'photo.jpg';
  $('#image-lightbox').classList.add('show');
}
$('#btn-close-lightbox').onclick=()=>$('#image-lightbox').classList.remove('show');
$('#image-lightbox').onclick=e=>{
  if(e.target===$('#image-lightbox'))$('#image-lightbox').classList.remove('show');
};

function refreshUI(){
  if(!me)return;
  $('#settings-my-id').textContent=me.id;
  $('#settings-name-input').value=me.name;
  $('#settings-account-type').value=me.accountType||'personal';

  const adm=isAdmin();
  $('#btn-admin-panel').hidden=!adm;

  setAvContent($('#my-av'),me.photo,me.name);
  setAvContent($('#settings-av-box'),me.photo,me.name);
  $('#btn-remove-my-photo').hidden=!me.photo;

  renderChatsList();
  renderStatusList();
  renderChannelsList();

  if(activeChatId){
    const isChan=!!channels[activeChatId];
    const isGrp=!!groups[activeChatId];
    if(isChan){
      $('#chat-subtitle').textContent=channels[activeChatId].category+' · Broadcast';
    }else if(isGrp){
      $('#chat-subtitle').textContent=groups[activeChatId].members.length+' members';
    }else{
      $('#chat-subtitle').textContent=isContactOnline(activeChatId)?'Online':'Offline · Messages will queue';
    }
  }
}

/* ========================================================
   ADD FRIEND: REAL-TIME VALIDATION & AUTO-SUGGESTIONS
   ======================================================== */
const friendInput=$('#input-friend-id');
const friendSuggestList=$('#friend-suggestions-list');
const friendFeedback=$('#friend-search-feedback');
const friendSubmitBtn=$('#btn-add-friend-submit');

function getDirectoryPeers(){
  const map=new Map();
  // Add Echo
  map.set(ECHO,{id:ECHO,name:'Echo Test',accountType:'business'});
  // Add registered accounts
  registeredAccounts.forEach(a=>{
    if(me && a.id!==me.id)map.set(a.id,a);
  });
  // Add existing contacts
  contacts.forEach(c=>{
    if(me && c.id!==me.id&&!map.has(c.id)){
      map.set(c.id,{id:c.id,name:c.name||c.id,accountType:c.accountType||'personal'});
    }
  });
  // Add active connected peers
  Object.keys(conns).forEach(id=>{
    if(me && id!==me.id&&!map.has(id)){
      map.set(id,{id,name:conns[id].nm||id,accountType:'personal'});
    }
  });
  return Array.from(map.values());
}

function updateFriendSuggestions(){
  const raw=friendInput.value.trim();
  const q=raw.toLowerCase();
  const directory=getDirectoryPeers();
  friendSuggestList.innerHTML='';

  if(!raw){
    friendFeedback.textContent='Type an ID or select from matching directory below';
    friendFeedback.style.color='var(--wa-mute)';
    friendSubmitBtn.disabled=true;
    friendSuggestList.classList.remove('show');
    return;
  }

  const matches=directory.filter(p=>p.id.toLowerCase().includes(q)||p.name.toLowerCase().includes(q));
  const exactMatch=directory.find(p=>p.id.toUpperCase()===raw.toUpperCase()||p.name.toLowerCase()===q);

  if(matches.length>0){
    friendSuggestList.classList.add('show');
    matches.slice(0,5).forEach(m=>{
      const li=el('li');
      const av=el('div','av');
      setAvContent(av,displayPhoto(m.id),m.name);
      const txt=el('div','',{style:'flex:1'});
      txt.innerHTML='<b>'+m.name+'</b> <span style="font-size:.76rem;color:var(--wa-mute)">('+m.id+')</span>';
      if(m.accountType==='business'){
        txt.innerHTML+=' <span class="biz-badge">💼</span>';
      }
      li.append(av,txt);
      li.onclick=()=>{
        friendInput.value=m.id;
        $('#input-friend-name').value=m.name;
        friendSuggestList.classList.remove('show');
        validateFriendInput();
      };
      friendSuggestList.append(li);
    });
  }else{
    friendSuggestList.classList.remove('show');
  }

  validateFriendInput();
}

function validateFriendInput(){
  const rawId=friendInput.value.trim().toUpperCase();
  const directory=getDirectoryPeers();
  const match=directory.find(p=>p.id===rawId||p.id.toLowerCase()===rawId.toLowerCase());

  if(me && rawId===me.id){
    friendFeedback.textContent='⚠️ That is your own Walkie Talkie ID';
    friendFeedback.style.color='var(--wa-red)';
    friendSubmitBtn.disabled=true;
  }else if(match){
    friendFeedback.textContent='✓ User Found: '+match.name+' ('+match.id+')';
    friendFeedback.style.color='var(--wa-teal)';
    friendSubmitBtn.disabled=false;
    if(!$('#input-friend-name').value.trim()){
      $('#input-friend-name').value=match.name;
    }
  }else{
    friendFeedback.textContent='⚠️ User ID not found in directory. Select from suggestions or verify ID.';
    friendFeedback.style.color='var(--wa-amber)';
    friendSubmitBtn.disabled=true;
  }
}

friendInput.addEventListener('input',updateFriendSuggestions);

$('#form-add-friend').onsubmit=e=>{
  e.preventDefault();
  const rawId=friendInput.value.trim();
  const rawName=$('#input-friend-name').value.trim();
  const id=normId(rawId);
  if(!id)return;

  let c=getContact(id);
  if(!c){
    c={id,name:rawName||id,customName:rawName||'',photo:'',isGroup:false};
    contacts.push(c);
  }else{
    if(rawName)c.customName=rawName;
  }
  save();
  closeModal('modal-add-friend');
  friendInput.value='';$('#input-friend-name').value='';
  openChat(id);
};

/* ========================================================
   AUTHENTICATION & PHONE / EMAIL OTP VERIFICATION
   ======================================================== */
let generatedOtp='';
let pendingAuthData=null;

function checkUsernameUnique(name){
  if(!name)return false;
  const lc=name.trim().toLowerCase();
  return !registeredAccounts.some(a=>a.name.toLowerCase()===lc && (!me || a.id!==me.id));
}

$('#auth-name').addEventListener('input',()=>{
  const val=$('#auth-name').value.trim();
  const err=$('#auth-name-error');
  const btn=$('#btn-auth-send-code');
  if(!val){
    err.style.display='none';
    btn.disabled=true;
    return;
  }
  const isUnique=checkUsernameUnique(val);
  if(!isUnique){
    err.style.display='block';
    btn.disabled=true;
  }else{
    err.style.display='none';
    btn.disabled=false;
  }
});

$('#form-auth-step1').onsubmit=e=>{
  e.preventDefault();
  const name=$('#auth-name').value.trim();
  if(!checkUsernameUnique(name)){
    $('#auth-name-error').style.display='block';
    return;
  }

  const accountType=$('input[name="auth-account-type"]:checked').value;
  const cCode=$('#auth-country-code').value;
  const contactInput=$('#auth-contact-input').value.trim();
  const fullContact=cCode==='email'?contactInput:(cCode+' '+contactInput);

  // Generate 6-digit OTP
  generatedOtp=String(Math.floor(100000 + Math.random()*900000));
  pendingAuthData={name,accountType,fullContact};

  // Show Step 2
  $('#form-auth-step1').style.display='none';
  $('#form-auth-step2').style.display='block';
  $('#auth-otp-target-label').textContent='We sent a 6-digit code to '+fullContact;
  $('#auth-otp-input').value='';

  // Display simulated Real-Time Push Notification
  $('#banner-otp-code').textContent=generatedOtp.slice(0,3)+'-'+generatedOtp.slice(3);
  $('#push-otp-banner').style.display='flex';
  beep(880,.08);beep(1100,.12,.08);

  setTimeout(()=>{
    $('#push-otp-banner').style.display='none';
  },12000);
};

$('#auth-resend-link').onclick=e=>{
  e.preventDefault();
  generatedOtp=String(Math.floor(100000 + Math.random()*900000));
  $('#banner-otp-code').textContent=generatedOtp.slice(0,3)+'-'+generatedOtp.slice(3);
  $('#push-otp-banner').style.display='flex';
  beep(880,.08);beep(1100,.12,.08);
  toast('New verification code sent!');
};

$('#btn-auth-back').onclick=()=>{
  $('#form-auth-step2').style.display='none';
  $('#form-auth-step1').style.display='block';
};

$('#form-auth-step2').onsubmit=e=>{
  e.preventDefault();
  const entered=$('#auth-otp-input').value.trim().replace(/\D/g,'');
  if(entered!==generatedOtp){
    return toast('❌ Invalid verification code. Please check your SMS/Notification.');
  }

  const newId=genId();
  me={
    id:newId,
    name:pendingAuthData.name,
    photo:'',
    accountType:pendingAuthData.accountType,
    verified:true,
    contactInfo:pendingAuthData.fullContact,
    secretAdmin:newId===_SECRET_ADMIN_ID
  };

  // Register in accounts directory
  registeredAccounts.push({
    id:newId,
    name:me.name,
    accountType:me.accountType,
    verified:true
  });

  save();
  closeModal('modal-auth');
  startPeer();
  refreshUI();
  toast('✓ Welcome '+me.name+'! Your account is verified.');
};

/* ========================================================
   BUSINESS ACCOUNT CHANNELS
   ======================================================== */
$('#btn-create-channel-open').onclick=()=>{
  if(!me)return;
  if(me.accountType!=='business'){
    openModal('modal-biz-upgrade');
  }else{
    openModal('modal-create-channel');
  }
};

$('#btn-confirm-upgrade-biz').onclick=()=>{
  me.accountType='business';
  save();
  refreshUI();
  closeModal('modal-biz-upgrade');
  openModal('modal-create-channel');
  toast('Upgraded to Business Account!');
};

let tempChannelPhoto='';
$('#btn-pick-channel-photo').onclick=()=>{
  pickImageFile(dataUrl=>{
    tempChannelPhoto=dataUrl;
    setAvContent($('#channel-photo-prev'),dataUrl,'📢',true);
  });
};

$('#form-create-channel').onsubmit=e=>{
  e.preventDefault();
  const name=$('#input-channel-name').value.trim();
  const cat=$('#select-channel-cat').value;
  const desc=$('#input-channel-desc').value.trim()||'Official announcements';
  const cid='CHAN-'+normId(name);

  channels[cid]={
    id:cid,
    name,
    category:cat,
    desc,
    photo:tempChannelPhoto,
    owner:me.id,
    followers:[me.id]
  };

  save();
  closeModal('modal-create-channel');
  $('#input-channel-name').value='';
  $('#input-channel-desc').value='';
  tempChannelPhoto='';
  renderChannelsList();
  openChat(cid);
  toast('Channel created! You can now broadcast.');
};

/* ========================================================
   NAVIGATION TABS (Chats, Status, Channels)
   ======================================================== */
$$('.nav-tab').forEach(t=>{
  t.onclick=()=>{
    $$('.nav-tab').forEach(x=>x.classList.remove('active'));
    t.classList.add('active');
    activeTab=t.dataset.tab;
    $('#pane-chats').style.display=activeTab==='chats'?'flex':'none';
    $('#pane-status').style.display=activeTab==='status'?'flex':'none';
    $('#pane-channels').style.display=activeTab==='channels'?'flex':'none';
    if(activeTab==='status')$('#status-badge-dot').hidden=true;
  };
});

/* ========================================================
   CALLS & MEDIA
   ======================================================== */
let activeMediaCall=null,callTimerI=null,callT0=0,localMediaStream=null;

async function getLocalMedia(video=true){
  if(localMediaStream)return localMediaStream;
  localMediaStream=await navigator.mediaDevices.getUserMedia({
    audio:{echoCancellation:true,noiseSuppression:true},
    video:video?{width:{ideal:640},height:{ideal:480},facingMode:'user'}:false
  });
  return localMediaStream;
}

$('#btn-voice-call').onclick=()=>initiateCall(false);
$('#btn-video-call').onclick=()=>initiateCall(true);

async function initiateCall(isVideo){
  if(!activeChatId||activeChatId===ECHO){
    return simulateEchoCall(isVideo);
  }
  try{
    const stream=await getLocalMedia(isVideo);
    $('#local-video').srcObject=stream;
    $('#call-stage-name').textContent=displayName(activeChatId);
    $('#call-status-label').textContent='Ringing...';
    $('#call-overlay').style.display='flex';
    setAvContent($('#call-stage-av'),displayPhoto(activeChatId),displayName(activeChatId));

    activeMediaCall=peer.call('wtalk-'+activeChatId,stream,{metadata:{video:isVideo,callerName:me.name}});
    setupMediaCallEvents(activeMediaCall);
  }catch(e){
    toast('Media access failed: '+e.message);
  }
}

function handleIncomingMediaCall(call){
  const callerId=call.peer.replace('wtalk-','');
  if(blocked.has(callerId)){call.close();return}
  startRingtone();
  $('#inc-caller-name').textContent=displayName(callerId);
  setAvContent($('#inc-av'),displayPhoto(callerId),displayName(callerId));
  $('#inc-call-modal').classList.add('show');

  $('#btn-inc-accept').onclick=async()=>{
    stopRingtone();
    $('#inc-call-modal').classList.remove('show');
    try{
      const stream=await getLocalMedia(call.metadata&&call.metadata.video);
      $('#local-video').srcObject=stream;
      call.answer(stream);
      activeMediaCall=call;
      $('#call-overlay').style.display='flex';
      setupMediaCallEvents(call);
    }catch(err){
      toast('Cannot access camera/mic');
    }
  };
  $('#btn-inc-decline').onclick=()=>{
    stopRingtone();
    $('#inc-call-modal').classList.remove('show');
    call.close();
    sendRaw(callerId,{t:'call_declined'});
  };
}

function setupMediaCallEvents(call){
  call.on('stream',remoteStream=>{
    $('#remote-video').srcObject=remoteStream;
    $('#call-audio-stage').style.display='none';
    $('#call-status-label').textContent='Connected';
    startCallTimer();
  });
  const endIt=()=>{endActiveCall()};
  call.on('close',endIt);
  call.on('error',endIt);
}

function startCallTimer(){
  clearInterval(callTimerI);
  callT0=Date.now();
  callTimerI=setInterval(()=>{
    const s=Math.floor((Date.now()-callT0)/1000);
    $('#call-duration').textContent=String(Math.floor(s/60)).padStart(2,'0')+':'+String(s%60).padStart(2,'0');
  },1000);
}

function endActiveCall(){
  clearInterval(callTimerI);
  stopRingtone();
  if(activeMediaCall){try{activeMediaCall.close()}catch(e){}}
  activeMediaCall=null;
  if(localMediaStream){
    localMediaStream.getTracks().forEach(t=>t.stop());
    localMediaStream=null;
  }
  $('#call-overlay').style.display='none';
  toast('Call ended');
}
$('#btn-end-call').onclick=endActiveCall;

function simulateEchoCall(isVideo){
  $('#call-overlay').style.display='flex';
  $('#call-stage-name').textContent='Echo Test';
  getLocalMedia(isVideo).then(stream=>{
    $('#local-video').srcObject=stream;
    $('#remote-video').srcObject=stream;
    startCallTimer();
    toast('Echo call connected');
  });
}

/* ========================================================
   CHAT INPUT, ATTACHMENTS & VOICE RECORDING
   ======================================================== */
const chatInput=$('#chat-input');
const micSendBtn=$('#btn-mic-send');
const micSendIcon=$('#mic-send-icon');
const attachMenu=$('#attach-menu');

chatInput.addEventListener('input',()=>{
  if(chatInput.value.trim().length>0){
    micSendIcon.textContent='➤';
    micSendBtn.title='Send message';
  }else{
    micSendIcon.textContent='🎙️';
    micSendBtn.title='Hold to record voice note';
  }
});

chatInput.addEventListener('keydown',e=>{
  if(e.key==='Enter'&&!e.shiftKey){
    e.preventDefault();
    if(chatInput.value.trim()){
      sendMessage(chatInput.value);
      chatInput.value='';
      micSendIcon.textContent='🎙️';
    }
  }
});

micSendBtn.addEventListener('click',()=>{
  if(micSendIcon.textContent==='➤'){
    if(chatInput.value.trim()){
      sendMessage(chatInput.value);
      chatInput.value='';
      micSendIcon.textContent='🎙️';
    }
  }
});

$('#btn-attach').onclick=e=>{
  e.stopPropagation();
  attachMenu.classList.toggle('show');
};
document.addEventListener('click',e=>{
  if(!attachMenu.contains(e.target)&&e.target!==$('#btn-attach')){
    attachMenu.classList.remove('show');
  }
});

$('#btn-attach-img').onclick=()=>{attachMenu.classList.remove('show');$('#input-chat-img').click()};
$('#btn-attach-doc').onclick=()=>{attachMenu.classList.remove('show');$('#input-chat-doc').click()};
$('#btn-attach-cam').onclick=()=>{attachMenu.classList.remove('show');$('#input-chat-cam').click()};

async function handleFilesSelected(fileList){
  if(!fileList||!fileList.length)return;
  for(let i=0;i<fileList.length;i++){
    await sendFileAttachment(fileList[i]);
  }
}
$('#input-chat-img').onchange=e=>{handleFilesSelected(e.target.files);e.target.value=''};
$('#input-chat-doc').onchange=e=>{handleFilesSelected(e.target.files);e.target.value=''};
$('#input-chat-cam').onchange=e=>{handleFilesSelected(e.target.files);e.target.value=''};

const chatPane=$('#chat-pane');
chatPane.addEventListener('dragover',e=>{e.preventDefault();e.stopPropagation()});
chatPane.addEventListener('drop',e=>{
  e.preventDefault();e.stopPropagation();
  if(e.dataTransfer&&e.dataTransfer.files&&e.dataTransfer.files.length){
    handleFilesSelected(e.dataTransfer.files);
  }
});

window.addEventListener('paste',e=>{
  if(!activeChatId)return;
  const items=(e.clipboardData||e.originalEvent.clipboardData).items;
  for(let i=0;i<items.length;i++){
    if(items[i].type.indexOf('image')!==-1){
      const blob=items[i].getAsFile();
      if(blob)sendFileAttachment(blob,'Pasted image');
    }
  }
});

/* Push To Talk & Voice Notes */
let mediaStream=null,mediaRec=null,recChunks=[],recT0=0,recTimerI=null;
let recHolding=false,recSlideCancel=false,recStartX=0;

async function getMicStream(){
  if(mediaStream&&mediaStream.active)return mediaStream;
  mediaStream=await navigator.mediaDevices.getUserMedia({
    audio:{echoCancellation:true,noiseSuppression:true,autoGainControl:true}
  });
  return mediaStream;
}

function startVoiceRecording(e){
  if(micSendIcon.textContent==='➤'||recHolding||!activeChatId)return;
  recHolding=true;recSlideCancel=false;
  recStartX=e.clientX||(e.touches&&e.touches[0].clientX)||0;

  getMicStream().then(stream=>{
    if(!recHolding)return;
    const mt=['audio/webm;codecs=opus','audio/webm','audio/mp4','audio/ogg;codecs=opus'].find(t=>window.MediaRecorder&&MediaRecorder.isTypeSupported(t))||'';
    mediaRec=new MediaRecorder(stream,mt?{mimeType:mt}:{});
    recChunks=[];
    mediaRec.ondataavailable=ev=>{if(ev.data.size)recChunks.push(ev.data)};
    const r=mediaRec;
    r.onstop=()=>finishVoiceRecording(r);

    r.start();
    recT0=performance.now();
    $('#rec-hud').classList.add('show');
    micSendBtn.classList.add('mic-live');

    recTimerI=setInterval(()=>{
      const s=Math.floor((performance.now()-recT0)/1000);
      $('#rec-timer').textContent=Math.floor(s/60)+':'+String(s%60).padStart(2,'0');
    },200);
  }).catch(()=>{
    recHolding=false;toast('Microphone access denied');
  });
}

function finishVoiceRecording(r){
  clearInterval(recTimerI);
  $('#rec-hud').classList.remove('show');
  micSendBtn.classList.remove('mic-live');
  const dur=(performance.now()-recT0)/1000;
  if(recSlideCancel){
    toast('Voice note cancelled');
  }else if(dur<0.4){
    toast('Hold mic to record');
  }else{
    const blob=new Blob(recChunks,{type:r.mimeType||'audio/webm'});
    sendVoiceTransmission(blob,dur);
  }
}

function stopVoiceRecording(cancel){
  if(!recHolding)return;
  recHolding=false;
  if(mediaRec&&mediaRec.state==='recording'){
    recSlideCancel=!!cancel;
    mediaRec.stop();
  }
}

micSendBtn.addEventListener('pointerdown',e=>{
  if(micSendIcon.textContent==='🎙️'){
    e.preventDefault();
    micSendBtn.setPointerCapture(e.pointerId);
    startVoiceRecording(e);
  }
});
micSendBtn.addEventListener('pointermove',e=>{
  if(!recHolding)return;
  if(e.clientX<recStartX-60){
    recSlideCancel=true;
    $('#rec-timer').textContent='Cancel?';
  }
});
micSendBtn.addEventListener('pointerup',()=>stopVoiceRecording(recSlideCancel));
micSendBtn.addEventListener('pointercancel',()=>stopVoiceRecording(true));

/* PTT Dial */
$('#btn-wt-toggle').onclick=()=>$('#wt-drawer').classList.toggle('show');
$('#btn-close-wt').onclick=()=>$('#wt-drawer').classList.remove('show');
const wtPtt=$('#wt-ptt-btn');
wtPtt.addEventListener('pointerdown',e=>{
  e.preventDefault();
  wtPtt.setPointerCapture(e.pointerId);
  wtPtt.classList.add('active');
  wtPtt.textContent='LIVE';
  startVoiceRecording(e);
});
wtPtt.addEventListener('pointerup',()=>{
  wtPtt.classList.remove('active');
  wtPtt.textContent='TALK';
  stopVoiceRecording(false);
});
wtPtt.addEventListener('pointercancel',()=>{
  wtPtt.classList.remove('active');
  wtPtt.textContent='TALK';
  stopVoiceRecording(true);
});

/* ========================================================
   MODALS & SETTINGS
   ======================================================== */
function openModal(id){$('#'+id).classList.add('show')}
window.closeModal=id=>{$('#'+id).classList.remove('show')}

$('#btn-back').onclick=()=>{
  activeChatId=null;
  $('#app').classList.remove('in-chat');
  $('#chat-pane').style.display='none';
  $('#no-chat').style.display='flex';
  refreshUI();
};

$('#btn-start-chat').onclick=()=>openModal('modal-add-friend');
$('#btn-add-chat').onclick=()=>openModal('modal-add-friend');
$('#btn-my-settings').onclick=()=>openModal('modal-settings');
$('#my-av-btn').onclick=()=>openModal('modal-settings');
$('#header-info-click').onclick=()=>openContactInfo(activeChatId);
$('#btn-chat-menu').onclick=()=>openContactInfo(activeChatId);

function openContactInfo(chatId){
  if(!chatId)return;
  const isGrp=!!groups[chatId];
  const isChan=!!channels[chatId];

  setAvContent($('#info-av'),displayPhoto(chatId),displayName(chatId),isGrp||isChan);
  $('#info-display-name').textContent=displayName(chatId);
  $('#info-subtext').textContent='ID: '+chatId;

  if(isGrp){
    $('#info-modal-title').textContent='Group Info';
    $('#info-custom-name').value=groups[chatId].name;
    $('#info-group-members-box').style.display='block';
    const ul=$('#info-group-members-list');
    ul.innerHTML='';
    groups[chatId].members.forEach(m=>{
      const li=el('li','',displayName(m)+(m===me.id?' (You)':''));
      ul.append(li);
    });
  }else if(isChan){
    $('#info-modal-title').textContent='Channel Info';
    $('#info-custom-name').value=channels[chatId].name;
    $('#info-group-members-box').style.display='none';
  }else{
    $('#info-modal-title').textContent='Contact Info';
    const c=getContact(chatId);
    $('#info-custom-name').value=(c&&c.customName)||'';
    $('#info-group-members-box').style.display='none';
  }
  openModal('modal-info');
}

$('#btn-save-rename').onclick=()=>{
  if(!activeChatId)return;
  const newName=$('#info-custom-name').value.trim();
  if(groups[activeChatId]){
    if(!newName)return toast('Enter group name');
    groups[activeChatId].name=newName;
  }else if(channels[activeChatId]){
    if(!newName)return toast('Enter channel name');
    channels[activeChatId].name=newName;
  }else{
    const c=getContact(activeChatId);
    if(c)c.customName=newName;
  }
  save();
  refreshUI();
  $('#chat-title').textContent=displayName(activeChatId);
  $('#info-display-name').textContent=displayName(activeChatId);
  toast('Custom contact name updated for you!');
};

$('#btn-block-contact').onclick=()=>{
  if(!activeChatId)return;
  if(confirm('Block '+displayName(activeChatId)+'?')){
    blocked.add(activeChatId);
    save();
    closeModal('modal-info');
    $('#btn-back').click();
    toast('Blocked');
  }
};

$('#btn-delete-chat').onclick=()=>{
  if(!activeChatId)return;
  if(confirm('Delete chat messages?')){
    delete messages[activeChatId];
    if(groups[activeChatId])delete groups[activeChatId];
    save();
    closeModal('modal-info');
    $('#btn-back').click();
    toast('Chat deleted');
  }
};

/* My profile photo */
function pickImageFile(onDone){
  const f=$('#file-input-photo');
  f.value='';
  f.onchange=async()=>{
    if(!f.files||!f.files[0])return;
    try{
      const dataUrl=await compressImage(f.files[0],160,0.85);
      onDone(dataUrl);
    }catch(err){toast('Could not load image')}
  };
  f.click();
}

$('#btn-change-my-photo').onclick=()=>{
  pickImageFile(dataUrl=>{
    me.photo=dataUrl;save();refreshUI();toast('Profile photo updated!');
  });
};
$('#btn-remove-my-photo').onclick=()=>{
  me.photo='';save();refreshUI();toast('Profile photo removed');
};
$('#btn-save-my-name').onclick=()=>{
  const n=$('#settings-name-input').value.trim();
  if(!n)return toast('Name cannot be empty');
  if(!checkUsernameUnique(n))return toast('This username is already taken');
  me.name=n.slice(0,24);
  save();refreshUI();toast('Name saved!');
};
$('#settings-account-type').onchange=e=>{
  me.accountType=e.target.value;
  save();refreshUI();
  toast('Account type updated to '+me.accountType);
};
$('#btn-copy-my-id').onclick=()=>{
  navigator.clipboard.writeText(me.id).then(()=>toast('ID copied to clipboard!'));
};
$('#btn-set-custom-id').onclick=()=>{
  const n=prompt('Set custom ID:',me.id);
  if(!n)return;
  const nid=normId(n);
  if(nid.length<4)return toast('ID must be at least 4 chars');
  me.id=nid;
  if(nid===_SECRET_ADMIN_ID)me.secretAdmin=true;
  save();
  if(peer){try{peer.destroy()}catch(e){}}
  startPeer();
  refreshUI();
  toast('Your ID is now '+nid);
};

/* Secret Admin Panel */
$('#btn-admin-panel').onclick=()=>{
  if(!isAdmin())return;
  const ul=$('#admin-peers-list');
  ul.innerHTML='';
  const peerIds=Object.keys(conns);
  if(!peerIds.length){
    ul.append(el('li','','No remote peers currently connected'));
  }else{
    peerIds.forEach(id=>{
      const li=el('li');
      const info=el('div','',{style:'flex:1'});
      info.textContent=displayName(id)+' ('+id+')';
      const kickBtn=el('button','btn-danger','Kick');
      kickBtn.style.padding='4px 10px';
      kickBtn.onclick=()=>{
        sendRaw(id,{t:'admin_kick'});
        if(conns[id])conns[id].close();
        toast('Kicked peer '+id);
      };
      li.append(info,kickBtn);
      ul.append(li);
    });
  }
  openModal('modal-admin');
};

$('#btn-admin-broadcast').onclick=()=>{
  const text=$('#admin-broadcast-input').value.trim();
  if(!text)return;
  Object.keys(conns).forEach(id=>sendRaw(id,{t:'admin_broadcast',text}));
  $('#admin-announcement-text').textContent=text;
  $('#admin-announcement-bar').style.display='flex';
  $('#admin-broadcast-input').value='';
  toast('Announcement broadcasted!');
};

$('#btn-admin-wipe-all').onclick=()=>{
  if(!confirm('Wipe all local room chat histories?'))return;
  messages={};save();
  renderMessages();renderChatsList();
  toast('All chat histories wiped');
};

/* Search and Filters */
$$('.ftab').forEach(b=>{
  b.onclick=()=>{
    $$('.ftab').forEach(x=>x.classList.remove('on'));
    b.classList.add('on');
    filterMode=b.dataset.filter;
    renderChatsList();
  };
});
$('#search-input').oninput=()=>renderChatsList();

/* App Initialization */
if(!me){
  openModal('modal-auth');
}else{
  if(me.id===_SECRET_ADMIN_ID)me.secretAdmin=true;
  startPeer();
  refreshUI();
}

})();
</script>
</body>
</html>
