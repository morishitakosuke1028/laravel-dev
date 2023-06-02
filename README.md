git clone<br>
cd laravel-dev<br>
mkdir -p src<br>
docker compose build<br>
docker compose up -d<br>
※createする際の注意点（バージョン）<br>
docker-compose exec app composer create-project --prefer-dist "laravel/laravel=8.4" . または↓↓<br>
docker compose exec app composer create-project --prefer-dist laravel/laravel .<br>
docker compose exec app php artisan key:generate<br>
docker compose exec app php artisan storage:link<br>
docker compose exec app chmod -R 777 storage bootstrap/cache<br>
docker compose exec app php artisan migrate<br>
<br>
docker-compose exec web /bin/bash<br>
apt-get update<br>
※適時バージョン修正<br>
curl -sL https://deb.nodesource.com/setup_14.x | bash -<br>
apt-get install -y nodejs<br>
node -v<br>
npm -v<br>
exit<br>

docker-compose exec app composer require laravel/ui:3.* <br>
docker-compose exec app php artisan ui react --auth <br>
docker compose exec web npm install <br>
docker-compose exec web npm run dev <br>
↑ npm run devでエラーが出た場合 <br>
package.json <br>
"laravel-mix": "^6.0.6", <br>
に変更 <br>
docker-compose exec web npm install <br>
docker-compose exec web npm run dev <br>
<br>
4項目削除<br>
<ul>
<li>/auth以下</li>
<li>layouts(app.blade.phpをviews直下に移動させlayoutsディレクトリ自体を削除)</li>
<li>home.blade.php</li>
<li>welcome.blade.php</li>
</ul>
<br>
resource→views→app.blade.phpになっていればOK
<br>
app.blade.phpのid="app"の中身を空にする
<br>




