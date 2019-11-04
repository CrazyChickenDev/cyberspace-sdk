### **Description**

Hi Pilot ! 

Cyberspace.dev is first online game for developers! In the game, you are the control center of spaceships in the universe, the game has a fairly simple game model and does not require much time to start. This is an excellent platform for both manned control and for the development of automation scripts and even artificial intelligence!

### **Quotas**

Requests: <b>5</b> per sec <br/>
Connections to API: <b>20</b> per <b>single IPAddress</b>

### **Quick start**

Install module as npm package

```javascript
npm install @cyberspace-dev/sdk
```

1. Connect to account service and signin

```typescript
const account = await Account.connect();
await account.signin('email@mail.com', 'password');
```

2. Look at what objects you own and select any ship

```typescript
const objects = await account.objects();
const target = objects.find((instance: any) => instance.type === 'Ship');
```

3. Take control over your ship

```typescript
const quadrant = await Sector.connect(target.realm, account.token);
const ship = await quadrant.get(target.uuid); 
```

4. Escape from the planet and move to any point in the system

```typescript
await ship.escape();
await ship.move(800, 800);
```

Congratulations! Please read our wiki.
